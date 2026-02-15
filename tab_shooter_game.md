<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tab Shooter Game</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            font-family: Arial, sans-serif;
        }
        #gameCanvas {
            display: block;
            background: #cce6ff;
        }
        #ui {
            position: absolute;
            top: 10px;
            left: 10px;
            color: #333;
            font-size: 18px;
            font-weight: bold;
            background: rgba(255,255,255,0.8);
            padding: 10px 20px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }
        #instructions {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            color: #333;
            background: rgba(255,255,255,0.9);
            padding: 15px 30px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }
        .victory {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(76, 175, 80, 0.95);
            color: white;
            padding: 40px 60px;
            border-radius: 20px;
            font-size: 32px;
            font-weight: bold;
            text-align: center;
            box-shadow: 0 4px 20px rgba(0,0,0,0.3);
            display: none;
        }
    </style>
</head>
<body>
    <canvas id="gameCanvas"></canvas>
    <div id="ui">
        <div>Score: <span id="score">0</span></div>
        <div>Tabs Opened: <span id="opened">0</span>/<span id="total">7</span></div>
    </div>
    <div id="instructions">
        <strong>Controls:</strong> WASD/Arrow Keys to move | Aim with Mouse | SPACE to shoot
    </div>
    <div id="victory" class="victory">
        🎉 All Tabs Opened! 🎉<br>
        <div style="font-size: 20px; margin-top: 20px;">Final Score: <span id="finalScore">0</span></div>
    </div>

    <script>
    window.onload = function() {
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        
        let score = 0;
        let tabsOpened = 0;
        let mouseX = 0;
        let mouseY = 0;
        
        /* PLAYER */
        const player = {
            x: 100,
            y: canvas.height - 120,
            width: 40,
            height: 50,
            speed: 5,
            color: '#4CAF50'
        };
        
        /* INPUT */
        const keys = {};
        window.addEventListener('keydown', e => keys[e.key.toLowerCase()] = true);
        window.addEventListener('keyup', e => keys[e.key.toLowerCase()] = false);
        window.addEventListener('mousemove', e => {
            mouseX = e.clientX;
            mouseY = e.clientY;
        });
        
        /* BULLETS */
        const bullets = [];
        let canShoot = true;
        window.addEventListener('keydown', e => {
            if (e.key === ' ' && canShoot) {
                const angle = Math.atan2(mouseY - player.y, mouseX - player.x);
                bullets.push({
                    x: player.x + 20,
                    y: player.y + 25,
                    vx: Math.cos(angle) * 10,
                    vy: Math.sin(angle) * 10,
                    r: 5
                });
                canShoot = false;
                setTimeout(() => canShoot = true, 200);
            }
        });
        
        /* PARTICLE EFFECTS */
        const particles = [];
        function createParticles(x, y, color) {
            for(let i = 0; i < 15; i++) {
                particles.push({
                    x: x,
                    y: y,
                    vx: (Math.random() - 0.5) * 6,
                    vy: (Math.random() - 0.5) * 6,
                    life: 60,
                    color: color
                });
            }
        }
        
        /* TABS */
        const names = [
            "Ticket Raise", "Hostels", "Student Profile",
            "Grades", "Attendance", "Fee", "Timetable"
        ];
        const tabs = [];
        const tabColors = ['#FF6B6B', '#4ECDC4', '#FFE66D', '#95E1D3', '#F38181', '#AA96DA', '#FCBAD3'];
        
        function setupTabs() {
            let startX = 200;
            let startY = 120;
            let gapX = 200;
            let gapY = 150;
            let cols = 4;
            for(let i = 0; i < names.length; i++) {
                let row = Math.floor(i / cols);
                let col = i % cols;
                tabs.push({
                    x: startX + col * gapX,
                    y: startY + row * gapY,
                    w: 150,
                    h: 70,
                    label: names[i],
                    health: 2,
                    max: 2,
                    color: tabColors[i],
                    opened: false,
                    shake: 0
                });
            }
        }
        setupTabs();
        
        /* UPDATE */
        function update() {
            // Player movement
            if(keys['w'] || keys['arrowup']) player.y -= player.speed;
            if(keys['s'] || keys['arrowdown']) player.y += player.speed;
            if(keys['a'] || keys['arrowleft']) player.x -= player.speed;
            if(keys['d'] || keys['arrowright']) player.x += player.speed;
            
            player.x = Math.max(0, Math.min(canvas.width - player.width, player.x));
            player.y = Math.max(0, Math.min(canvas.height - player.height, player.y));
            
            // Bullets
            for(let i = bullets.length - 1; i >= 0; i--) {
                bullets[i].x += bullets[i].vx;
                bullets[i].y += bullets[i].vy;
                
                if(bullets[i].x < 0 || bullets[i].x > canvas.width ||
                   bullets[i].y < 0 || bullets[i].y > canvas.height) {
                    bullets.splice(i, 1);
                    continue;
                }
                
                // Collision with tabs
                for(let tab of tabs) {
                    if(!tab.opened && bullets[i] &&
                       bullets[i].x > tab.x &&
                       bullets[i].x < tab.x + tab.w &&
                       bullets[i].y > tab.y &&
                       bullets[i].y < tab.y + tab.h) {
                        tab.health--;
                        tab.shake = 10;
                        score += 10;
                        createParticles(bullets[i].x, bullets[i].y, tab.color);
                        bullets.splice(i, 1);
                        
                        if(tab.health <= 0) {
                            tab.opened = true;
                            tabsOpened++;
                            score += 50;
                            createParticles(tab.x + tab.w/2, tab.y + tab.h/2, '#FFD700');
                            
                            // Check victory
                            if(tabsOpened === tabs.length) {
                                document.getElementById('victory').style.display = 'block';
                                document.getElementById('finalScore').textContent = score;
                            }
                        }
                        break;
                    }
                }
            }
            
            // Particles
            for(let i = particles.length - 1; i >= 0; i--) {
                particles[i].x += particles[i].vx;
                particles[i].y += particles[i].vy;
                particles[i].life--;
                if(particles[i].life <= 0) {
                    particles.splice(i, 1);
                }
            }
            
            // Update shake
            tabs.forEach(tab => {
                if(tab.shake > 0) tab.shake--;
            });
            
            // Update UI
            document.getElementById('score').textContent = score;
            document.getElementById('opened').textContent = tabsOpened;
        }
        
        /* DRAW */
        function draw() {
            // Background
            ctx.fillStyle = "#cce6ff";
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            // Tabs
            for(let tab of tabs) {
                ctx.save();
                
                // Shake effect
                if(tab.shake > 0) {
                    ctx.translate(Math.random() * tab.shake - tab.shake/2, 
                                  Math.random() * tab.shake - tab.shake/2);
                }
                
                if(tab.opened) {
                    // Opened tab
                    ctx.fillStyle = "#90EE90";
                    ctx.fillRect(tab.x, tab.y, tab.w, tab.h);
                    ctx.strokeStyle = "#32CD32";
                    ctx.lineWidth = 3;
                    ctx.strokeRect(tab.x, tab.y, tab.w, tab.h);
                    
                    // Checkmark
                    ctx.strokeStyle = "#228B22";
                    ctx.lineWidth = 4;
                    ctx.beginPath();
                    ctx.moveTo(tab.x + 30, tab.y + 35);
                    ctx.lineTo(tab.x + 50, tab.y + 50);
                    ctx.lineTo(tab.x + 120, tab.y + 20);
                    ctx.stroke();
                } else {
                    // Active tab
                    ctx.fillStyle = tab.color;
                    ctx.fillRect(tab.x, tab.y, tab.w, tab.h);
                    ctx.strokeStyle = "#333";
                    ctx.lineWidth = 2;
                    ctx.strokeRect(tab.x, tab.y, tab.w, tab.h);
                    
                    // Health bar
                    const healthPercent = tab.health / tab.max;
                    ctx.fillStyle = "#333";
                    ctx.fillRect(tab.x + 10, tab.y + tab.h - 15, tab.w - 20, 8);
                    ctx.fillStyle = healthPercent > 0.5 ? "#4CAF50" : "#FF5252";
                    ctx.fillRect(tab.x + 10, tab.y + tab.h - 15, (tab.w - 20) * healthPercent, 8);
                }
                
                // Label
                ctx.fillStyle = tab.opened ? "#228B22" : "#333";
                ctx.font = "bold 14px Arial";
                ctx.textAlign = "center";
                ctx.fillText(tab.label, tab.x + tab.w/2, tab.y + 35);
                
                ctx.restore();
            }
            
            // Particles
            particles.forEach(p => {
                const alpha = p.life / 60;
                ctx.fillStyle = p.color;
                ctx.globalAlpha = alpha;
                ctx.beginPath();
                ctx.arc(p.x, p.y, 3, 0, Math.PI * 2);
                ctx.fill();
                ctx.globalAlpha = 1;
            });
            
            // Bullets
            ctx.fillStyle = "#FF5722";
            bullets.forEach(b => {
                ctx.beginPath();
                ctx.arc(b.x, b.y, b.r, 0, Math.PI * 2);
                ctx.fill();
            });
            
            // Player
            ctx.fillStyle = player.color;
            ctx.fillRect(player.x, player.y, player.width, player.height);
            ctx.fillStyle = "#2E7D32";
            ctx.fillRect(player.x + 5, player.y + 5, player.width - 10, player.height - 10);
            
            // Aiming line
            ctx.strokeStyle = "rgba(255, 87, 34, 0.3)";
            ctx.lineWidth = 2;
            ctx.setLineDash([5, 5]);
            ctx.beginPath();
            ctx.moveTo(player.x + 20, player.y + 25);
            ctx.lineTo(mouseX, mouseY);
            ctx.stroke();
            ctx.setLineDash([]);
        }
        
        /* GAME LOOP */
        function gameLoop() {
            update();
            draw();
            requestAnimationFrame(gameLoop);
        }
        
        gameLoop();
    }
    </script>
</body>
</html>
