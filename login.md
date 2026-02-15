<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Login - College Portal</title>
    <style>
        body { font-family: 'Segoe UI', sans-serif; background: linear-gradient(135deg, #667eea, #764ba2); height: 100vh; display: flex; align-items: center; justify-content: center; margin: 0; }
        .login-box { background: white; padding: 40px; border-radius: 15px; box-shadow: 0 10px 25px rgba(0,0,0,0.2); width: 350px; text-align: center; }
        input { width: 100%; padding: 12px; margin: 10px 0; border: 2px solid #ddd; border-radius: 8px; box-sizing: border-box; }
        button { width: 100%; padding: 12px; background: #667eea; color: white; border: none; border-radius: 8px; font-weight: bold; cursor: pointer; }
        button:hover { background: #764ba2; }
    </style>
</head>
<body>
    <div class="login-box">
        <h2>🎓 Portal Login</h2>
        <input type="text" id="username" placeholder="Roll Number (e.g., CSE-2021-145)">
        <input type="password" id="password" placeholder="Password">
        <button onclick="handleLogin()">Login</button>
        <p id="message" style="color: red; font-size: 14px;"></p>
    </div>

    <script>
        async function handleLogin() {
            const user = document.getElementById('username').value;
            const pass = document.getElementById('password').value;

            const response = await fetch('/api/login', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ username: user, password: pass })
            });

            const result = await response.json();
            if (result.success) {
                window.location.href = 'index.html'; // Redirect to the game
            } else {
                document.getElementById('message').textContent = result.message;
            }
        }
    </script>
</body>
</html>
