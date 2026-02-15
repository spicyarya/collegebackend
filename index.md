<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CONTRA: College Portal Mission</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

•⁠  ⁠{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    margin: 0;
    overflow: hidden;
    font-family: 'Press Start 2P', cursive;
    background: #000;
    image-rendering: pixelated;
    image-rendering: -moz-crisp-edges;
    image-rendering: crisp-edges;
}

#collegeName {
    position: absolute;
    top: 15px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 18px;
    color: #00ff00;
    background: rgba(0,0,0,0.85);
    padding: 12px 25px;
    border: 3px solid #00ff00;
    box-shadow: 0 0 20px #00ff00, inset 0 0 10px rgba(0,255,0,0.2);
    z-index: 1000;
    text-transform: uppercase;
    letter-spacing: 2px;
}

#gameCanvas {
    display: block;
    background: #1a1a2e;
}

#ui {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    color: #fff;
    font-size: 14px;
    background: #000;
    padding: 10px 40px;
    border-top: 4px solid #ff0000;
    display: flex;
    justify-content: space-between;
    box-shadow: 0 -5px 20px #ff0000;
}


#ui .label {
    color: #ffaa00;
}

#instructions {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    color: #fff;
    background: rgba(0,0,0,0.85);
    padding: 15px 30px;
    border: 3px solid #0099ff;
    text-align: center;
    box-shadow: 0 0 15px #0099ff;
    font-size: 10px;
    line-height: 1.6;
}

.notification {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: rgba(0, 0, 0, 0.95);
    color: #00ff00;
    padding: 40px 60px;
    border: 5px solid #00ff00;
    font-size: 20px;
    text-align: center;
    box-shadow: 0 0 30px #00ff00, inset 0 0 20px rgba(0,255,0,0.1);
    display: none;
    z-index: 2000;
    animation: pulseGlow 1s infinite;
}

@keyframes pulseGlow {
    0%, 100% { box-shadow: 0 0 30px #00ff00, inset 0 0 20px rgba(0,255,0,0.1); }
    50% { box-shadow: 0 0 50px #00ff00, inset 0 0 30px rgba(0,255,0,0.2); }
}

.notification button {
    margin: 15px 10px 5px;
    padding: 12px 30px;
    font-size: 12px;
    border: 3px solid;
    cursor: pointer;
    font-family: 'Press Start 2P', cursive;
    text-transform: uppercase;
    transition: all 0.2s;
}

.open-btn { 
    background: #00ff00; 
    color: #000; 
    border-color: #00ff00;
    box-shadow: 0 0 15px #00ff00;
}

.open-btn:hover {
    background: #00cc00;
    box-shadow: 0 0 25px #00ff00;
}

.close-btn { 
    background: #ff0000; 
    color: #fff; 
    border-color: #ff0000;
    box-shadow: 0 0 15px #ff0000;
}

.close-btn:hover {
    background: #cc0000;
    box-shadow: 0 0 25px #ff0000;
}

#startScreen {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(180deg, #0f0f1e 0%, #1a1a2e 50%, #0f0f1e 100%);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 3000;
    color: #fff;
}

#startScreen h1 {
    font-size: 48px;
    color: #ff0000;
    text-shadow: 0 0 20px #ff0000, 4px 4px 0 #000;
    margin-bottom: 20px;
    animation: titlePulse 2s infinite;
}

@keyframes titlePulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
}

#startScreen h2 {
    font-size: 24px;
    color: #00ff00;
    text-shadow: 0 0 15px #00ff00, 2px 2px 0 #000;
    margin-bottom: 40px;
}

#startScreen button {
    padding: 20px 50px;
    font-size: 16px;
    font-family: 'Press Start 2P', cursive;
    background: #ff0000;
    color: #fff;
    border: 4px solid #fff;
    cursor: pointer;
    box-shadow: 0 0 30px #ff0000;
    animation: buttonBlink 1.5s infinite;
}

@keyframes buttonBlink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.7; }
}

#startScreen button:hover {
    background: #cc0000;
    transform: scale(1.1);
}

.mission-text {
    font-size: 12px;
    color: #ffaa00;
    text-align: center;
    max-width: 600px;
    margin: 30px;
    line-height: 1.8;
    text-shadow: 2px 2px 0 #000;
}

</style>
</head>

<body>

<div id="startScreen">
    <h1>CONTRA</h1>
    <h2>COLLEGE PORTAL MISSION</h2>
    <p class="mission-text">
        MISSION BRIEFING:<br>
        INFILTRATE THE COLLEGE PORTAL SYSTEM<br>
        DESTROY ALL LOCKED SECTIONS<br>
        UNLOCK ACCESS TO VITAL INFORMATION
    </p>
    <button id="startBtn">PRESS START</button>
</div>

<div id="collegeName">ABC COLLEGE OF ENGINEERING</div>

<canvas id="gameCanvas"></canvas>

<div id="ui">
    <div><span class="label">SCORE:</span> <span id="score">0000000</span></div>
    <div><span class="label">LIVES:</span> <span id="lives">❤❤❤</span></div>
    <div><span class="label">AMMO:</span> <span id="ammo">∞</span></div>
</div>

<div id="instructions">
    <strong>CONTROLS:</strong><br>
    WASD/ARROWS: MOVE | MOUSE: AIM | SPACE: FIRE
</div>

<div id="notification" class="notification">
    <div id="notificationText"></div>
    <div style="margin-top:25px;">
        <button class="open-btn" id="openBtn">OPEN PORTAL</button>
        <button class="close-btn" id="closeBtn">CONTINUE MISSION</button>
    </div>
</div>

<script>
const startScreen = document.getElementById('startScreen');
const startBtn = document.getElementById('startBtn');

startBtn.addEventListener('click', () => {
    startScreen.style.display = 'none';
    initGame();
});

function initGame() {

const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

let score = 0;
let mouseX = 0;
let mouseY = 0;
let gamePaused = false;
let particles = [];
let explosions = [];

// Parallax background layers
const bgLayers = [
    { y: 0, speed: 0.5, color: '#0a0a15' },
    { y: 0, speed: 1, color: '#15152e' },
    { y: 0, speed: 1.5, color: '#1a1a2e' }
];

/* PLAYER - Contra soldier style */
const player = {
    x: 100,
    y: canvas.height - 150,
    width: 35,
    height: 45,
    speed: 6,
    color: '#00aaff',
    animFrame: 0,
    animSpeed: 0,
    direction: 1,
    jumping: false,
    jumpVelocity: 0,
    gravity: 0.8,
    onGround: false
};

/* INPUT */
const keys = {};
window.addEventListener('keydown', e => {
    if(!gamePaused) keys[e.key.toLowerCase()] = true;
});
window.addEventListener('keyup', e => keys[e.key.toLowerCase()] = false);
window.addEventListener('mousemove', e => {
    mouseX = e.clientX;
    mouseY = e.clientY;
});

/* BULLETS - Contra style */
const bullets = [];
let canShoot = true;
let bulletType = 0; // 0: normal, 1: spread

window.addEventListener('keydown', e => {
    if(e.key === ' ' && canShoot && !gamePaused) {
        const angle = Math.atan2(mouseY - player.y, mouseX - player.x);
        
        // Main bullet
        bullets.push({
            x: player.x + 20,
            y: player.y + 22,
            vx: Math.cos(angle) * 12,
            vy: Math.sin(angle) * 12,
            r: 4,
            color: '#ffff00',
            trail: []
        });
        
        // Muzzle flash particles
        for(let i = 0; i < 5; i++) {
            particles.push({
                x: player.x + 20,
                y: player.y + 22,
                vx: (Math.random() - 0.5) * 4,
                vy: (Math.random() - 0.5) * 4,
                life: 20,
                maxLife: 20,
                color: '#ffaa00'
            });
        }
        
        canShoot = false;
        setTimeout(()=> canShoot = true, 150);
    }
});

/* PORTAL TABS - Enemy bunker style */
const tabData = [
    { name: "TICKET RAISE", url: "ticket-raise.html", color: '#ff3333' },
    { name: "HOSTELS", url: "hostels.html", color: '#ff6633' },
    { name: "STUDENT PROFILE", url: "student-profile.html", color: '#ff9933' },
    { name: "GRADES", url: "grades.html", color: '#ffcc33' },
    { name: "ATTENDANCE", url: "attendance.html", color: '#33ff33' },
    { name: "FEE PORTAL", url: "fee.html", color: '#33ccff' },
    { name: "TIMETABLE", url: "timetable.html", color: '#9933ff' }
];

const tabs = [];

function setupTabs() {
    // Calculate dynamic spacing based on canvas width
    const totalWidth = canvas.width - 300; // Leave margins
    const cols = 4; // More columns for better distribution
    const rows = Math.ceil(tabData.length / cols);
    const gapX = totalWidth / cols;
    const startX = 200;
    const startY = 100;
    const gapY = 180;

    for(let i = 0; i < tabData.length; i++) {
        let row = Math.floor(i / cols);
        let col = i % cols;
        tabs.push({
            x: startX + col * gapX,
            y: startY + row * gapY,
            w: 180,
            h: 90,
            label: tabData[i].name,
            url: tabData[i].url,
            health: 3,
            max: 3,
            color: tabData[i].color,
            shake: 0,
            animOffset: Math.random() * Math.PI * 2,
            destroyed: false,
            shields: []
        });
        
        // Add shield particles around tab
        for(let j = 0; j < 8; j++) {
            tabs[i].shields.push({
                angle: (j / 8) * Math.PI * 2,
                distance: 70,
                active: true
            });
        }
    }
}
setupTabs();

/* EXPLOSION EFFECT */
function createExplosion(x, y, size) {
    for(let i = 0; i < size; i++) {
        const angle = Math.random() * Math.PI * 2;
        const speed = Math.random() * 6 + 2;
        particles.push({
            x: x,
            y: y,
            vx: Math.cos(angle) * speed,
            vy: Math.sin(angle) * speed,
            life: 40,
            maxLife: 40,
            color: i % 3 === 0 ? '#ff0000' : (i % 3 === 1 ? '#ff9900' : '#ffff00')
        });
    }
    
    explosions.push({
        x: x,
        y: y,
        radius: 5,
        maxRadius: size * 2,
        life: 30
    });
}

/* NOTIFICATION */
function showNotification(tabName, tabUrl) {
    gamePaused = true;
    const notification = document.getElementById('notification');
    document.getElementById('notificationText').textContent = "🎯 " + tabName + " UNLOCKED! 🎯";
    notification.style.display = 'block';

    document.getElementById('openBtn').onclick = () => {
        window.open(tabUrl, '_blank');
        closeNotification();
    };

    document.getElementById('closeBtn').onclick = closeNotification;
}

function closeNotification() {
    document.getElementById('notification').style.display = 'none';
    gamePaused = false;
}

/* UPDATE */
function update() {
    if(gamePaused) return;

    // Player movement
    let moving = false;
    if(keys['w'] || keys['arrowup']) {
        player.y -= player.speed;
        moving = true;
    }
    if(keys['s'] || keys['arrowdown']) {
        player.y += player.speed;
        moving = true;
    }
    if(keys['a'] || keys['arrowleft']) {
        player.x -= player.speed;
        player.direction = -1;
        moving = true;
    }
    if(keys['d'] || keys['arrowright']) {
        player.x += player.speed;
        player.direction = 1;
        moving = true;
    }

    if(moving) {
        player.animSpeed += 0.3;
        if(player.animSpeed > 4) {
            player.animFrame = (player.animFrame + 1) % 2;
            player.animSpeed = 0;
        }
    }

    player.x = Math.max(0, Math.min(canvas.width - player.width, player.x));
    player.y = Math.max(0, Math.min(canvas.height - player.height, player.y));

    // Bullets
    for(let i = bullets.length - 1; i >= 0; i--) {
        bullets[i].x += bullets[i].vx;
        bullets[i].y += bullets[i].vy;
        
        // Bullet trail
        bullets[i].trail.push({ x: bullets[i].x, y: bullets[i].y });
        if(bullets[i].trail.length > 5) bullets[i].trail.shift();

        if(bullets[i].x < 0 || bullets[i].x > canvas.width ||
           bullets[i].y < 0 || bullets[i].y > canvas.height) {
            bullets.splice(i, 1);
            continue;
        }

        // Check collision with tabs
        for(let tab of tabs) {
            if(!tab.destroyed && bullets[i] &&
               bullets[i].x > tab.x &&
               bullets[i].x < tab.x + tab.w &&
               bullets[i].y > tab.y &&
               bullets[i].y < tab.y + tab.h) {

                tab.health--;
                score += 100;
                tab.shake = 10;
                
                createExplosion(bullets[i].x, bullets[i].y, 15);
                bullets.splice(i, 1);

                if(tab.health <= 0) {
                    createExplosion(tab.x + tab.w/2, tab.y + tab.h/2, 40);
                    showNotification(tab.label, tab.url);
                    score += 1000;
                    tab.destroyed = true;
                    
                    // Respawn after 3 seconds
                    setTimeout(() => {
                        tab.health = tab.max;
                        tab.destroyed = false;
                    }, 3000);
                }
                break;
            }
        }
    }

    // Particles
    for(let i = particles.length - 1; i >= 0; i--) {
        particles[i].x += particles[i].vx;
        particles[i].y += particles[i].vy;
        particles[i].vy += 0.2; // Gravity
        particles[i].life--;
        
        if(particles[i].life <= 0) {
            particles.splice(i, 1);
        }
    }

    // Explosions
    for(let i = explosions.length - 1; i >= 0; i--) {
        explosions[i].radius += 2;
        explosions[i].life--;
        
        if(explosions[i].life <= 0) {
            explosions.splice(i, 1);
        }
    }

    // Tab animations
    for(let tab of tabs) {
        if(tab.shake > 0) tab.shake--;
        tab.animOffset += 0.05;
        
        // Animate shields
        for(let shield of tab.shields) {
            shield.angle += 0.03;
        }
    }

    // Update score display
    document.getElementById('score').textContent = String(score).padStart(7, '0');
}

/* DRAW */
function draw() {
    // Sky gradient
    const gradient = ctx.createLinearGradient(0, 0, 0, canvas.height);
    gradient.addColorStop(0, '#0a0a15');
    gradient.addColorStop(0.5, '#1a1a2e');
    gradient.addColorStop(1, '#0f0f1e');
    ctx.fillStyle = gradient;
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    // Grid background
    ctx.strokeStyle = 'rgba(0, 255, 0, 0.1)';
    ctx.lineWidth = 1;
    for(let i = 0; i < canvas.width; i += 40) {
        ctx.beginPath();
        ctx.moveTo(i, 0);
        ctx.lineTo(i, canvas.height);
        ctx.stroke();
    }
    for(let i = 0; i < canvas.height; i += 40) {
        ctx.beginPath();
        ctx.moveTo(0, i);
        ctx.lineTo(canvas.width, i);
        ctx.stroke();
    }

    // Draw tabs (portal sections)
    for(let tab of tabs) {
        if(tab.destroyed) continue;
        
        const shakeX = tab.shake > 0 ? (Math.random() - 0.5) * tab.shake : 0;
        const shakeY = tab.shake > 0 ? (Math.random() - 0.5) * tab.shake : 0;
        
        // Shield effect
        ctx.strokeStyle = tab.color;
        ctx.lineWidth = 2;
        for(let shield of tab.shields) {
            const sx = tab.x + tab.w/2 + Math.cos(shield.angle) * shield.distance;
            const sy = tab.y + tab.h/2 + Math.sin(shield.angle) * shield.distance;
            ctx.globalAlpha = 0.3;
            ctx.beginPath();
            ctx.arc(sx, sy, 4, 0, Math.PI * 2);
            ctx.stroke();
        }
        ctx.globalAlpha = 1;
        
        // Main tab body
        ctx.fillStyle = tab.color;
        ctx.fillRect(tab.x + shakeX, tab.y + shakeY, tab.w, tab.h);
        
        // Border glow
        ctx.strokeStyle = '#fff';
        ctx.lineWidth = 3;
        ctx.strokeRect(tab.x + shakeX, tab.y + shakeY, tab.w, tab.h);
        
        // Inner detail
        ctx.strokeStyle = '#000';
        ctx.lineWidth = 1;
        ctx.strokeRect(tab.x + 5 + shakeX, tab.y + 5 + shakeY, tab.w - 10, tab.h - 10);

        // Label
        ctx.fillStyle = '#fff';
        ctx.font = 'bold 11px "Press Start 2P"';
        ctx.textAlign = 'center';
        ctx.shadowColor = '#000';
        ctx.shadowBlur = 8;
        const lines = tab.label.split(' ');
        lines.forEach((line, idx) => {
            ctx.fillText(line, tab.x + tab.w/2 + shakeX, tab.y + 30 + idx * 15 + shakeY);
        });
        ctx.shadowBlur = 0;

        // Health bar
        const barWidth = tab.w - 20;
        const barHeight = 8;
        const barX = tab.x + 10 + shakeX;
        const barY = tab.y + tab.h - 18 + shakeY;
        
        ctx.fillStyle = '#000';
        ctx.fillRect(barX, barY, barWidth, barHeight);
        
        const healthPercent = tab.health / tab.max;
        const healthColor = healthPercent > 0.6 ? '#00ff00' : (healthPercent > 0.3 ? '#ffff00' : '#ff0000');
        ctx.fillStyle = healthColor;
        ctx.fillRect(barX, barY, barWidth * healthPercent, barHeight);
        
        ctx.strokeStyle = '#fff';
        ctx.lineWidth = 2;
        ctx.strokeRect(barX, barY, barWidth, barHeight);
    }

    // Draw particles
    for(let p of particles) {
        ctx.globalAlpha = p.life / p.maxLife;
        ctx.fillStyle = p.color;
        ctx.fillRect(p.x - 2, p.y - 2, 4, 4);
    }
    ctx.globalAlpha = 1;

    // Draw explosions
    for(let exp of explosions) {
        ctx.globalAlpha = exp.life / 30;
        ctx.strokeStyle = exp.life > 15 ? '#ffff00' : '#ff6600';
        ctx.lineWidth = 3;
        ctx.beginPath();
        ctx.arc(exp.x, exp.y, exp.radius, 0, Math.PI * 2);
        ctx.stroke();
    }
    ctx.globalAlpha = 1;

    // Draw bullets with trail
    for(let b of bullets) {
        // Trail
        ctx.strokeStyle = 'rgba(255, 255, 0, 0.3)';
        ctx.lineWidth = 3;
        ctx.beginPath();
        if(b.trail.length > 0) {
            ctx.moveTo(b.trail[0].x, b.trail[0].y);
            for(let t of b.trail) {
                ctx.lineTo(t.x, t.y);
            }
        }
        ctx.stroke();
        
        // Bullet
        ctx.fillStyle = b.color;
        ctx.shadowColor = b.color;
        ctx.shadowBlur = 10;
        ctx.beginPath();
        ctx.arc(b.x, b.y, b.r, 0, Math.PI * 2);
        ctx.fill();
        ctx.shadowBlur = 0;
    }

    // Draw player (Contra soldier)
    const px = player.x;
    const py = player.y;
    
    // Body
    ctx.fillStyle = player.color;
    ctx.fillRect(px + 8, py + 15, 20, 25);
    
    // Head
    ctx.fillStyle = '#ffcc99';
    ctx.fillRect(px + 12, py + 5, 12, 12);
    
    // Legs (animated)
    ctx.fillStyle = '#004488';
    if(player.animFrame === 0) {
        ctx.fillRect(px + 10, py + 38, 6, 7);
        ctx.fillRect(px + 20, py + 38, 6, 7);
    } else {
        ctx.fillRect(px + 8, py + 38, 6, 7);
        ctx.fillRect(px + 22, py + 38, 6, 7);
    }
    
    // Gun
    const angle = Math.atan2(mouseY - py, mouseX - px);
    ctx.save();
    ctx.translate(px + 18, py + 22);
    ctx.rotate(angle);
    ctx.fillStyle = '#666';
    ctx.fillRect(0, -2, 15, 4);
    ctx.restore();
    
    // Outline
    ctx.strokeStyle = '#000';
    ctx.lineWidth = 2;
    ctx.strokeRect(px + 8, py + 15, 20, 25);
    ctx.strokeRect(px + 12, py + 5, 12, 12);
}

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
