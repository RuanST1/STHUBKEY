<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Key Generator</title>
</head>
<body>
    <h1>Get Your Key</h1>
    <p>Enter your Roblox username to generate your key:</p>
    <input type="text" id="username" placeholder="Enter your Roblox username">
    <button onclick="generateKey()">Generate Key</button>
    <p id="key" style="margin-top: 20px; font-weight: bold;"></p>
    <script>
        function generateKey() {
            const username = document.getElementById("username").value;
            if (!username) {
                alert("Please enter your username.");
                return;
            }

            // Generate a unique key
            const key = btoa(username + "_" + Date.now());
            document.getElementById("key").innerText = `Your Key: ${key}`;

            // Optionally copy the key to clipboard
            navigator.clipboard.writeText(key).then(() => {
                alert("Key copied to clipboard!");
            });
        }
    </script>
</body>
</html>
