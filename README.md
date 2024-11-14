
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Password Generator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            text-align: center;
            width: 100%;
            max-width: 400px;
        }
        input[type="number"] {
            width: 100px;
            padding: 8px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .password {
            font-size: 1.5em;
            margin-top: 20px;
            color: #333;
            word-wrap: break-word;
        }
    </style>
</head>
<body>

<div class="container">
    <h2>Password Generator</h2>
    <p>Generate a random password with specified length</p>
    <label for="length">Password Length:</label>
    <input type="number" id="length" value="12" min="6" max="30">
    <br>
    <button onclick="generatePassword()">Generate Password</button>
    <div class="password" id="password"></div>
</div>

<script>
    function generatePassword() {
        var length = document.getElementById('length').value;
        var characters = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()_+[]{}|;:,.<>?";
        var password = '';
        
        for (var i = 0; i < length; i++) {
            var randomIndex = Math.floor(Math.random() * characters.length);
            password += characters[randomIndex];
        }

        document.getElementById('password').textContent = password;
    }
</script>

</body>
</html>
