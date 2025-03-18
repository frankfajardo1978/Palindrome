# Palindrome
Creación de un Palindromo

## En este 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Palindrome Checker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
            background-color: #f4f4f4;
        }
        #container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px gray;
            display: inline-block;
        }
        #text-input, #check-btn {
            margin: 10px;
            padding: 10px;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <div id="container">
        <h1>Palindrome Checker</h1>
        <input type="text" id="text-input" placeholder="Enter text">
        <button id="check-btn">Check</button>
        <p id="result"></p>
    </div>

    <script>
        function cleanText(text) {
            return text.replace(/[^a-zA-Z0-9]/g, "").toLowerCase();
        }

        function palindrome(str) {
            const cleaned = cleanText(str);
            const reversed = cleaned.split("").reverse().join("");
            return cleaned === reversed;
        }

        document.getElementById("check-btn").addEventListener("click", function() {
            const inputField = document.getElementById("text-input");
            const resultField = document.getElementById("result");
            let text = inputField.value;

            if (!text) {
                alert("Please input a value");
                return;
            }

            if (palindrome(text)) {
                resultField.textContent = `${text} is a palindrome.`;
            } else {
                resultField.textContent = `${text} is not a palindrome.`;
            }
        });
    </script>
</body>
</html>
