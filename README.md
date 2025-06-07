<!DOCTYPE html>
<html>
<head>
    <title>Simple Web Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f8ff;
            text-align: center;
            padding: 50px;
        }

        h1 {
            color: #333;
        }

        p {
            font-size: 18px;
            color: #555;
        }

        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 12px 24px;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

    <h1>Welcome to My Web Page</h1>
    <p>This page is styled with CSS and uses JavaScript for interactivity.</p>

    <button onclick="showMessage()">Click Me!</button>

    <script>
        function showMessage() {
            alert("Hello! You clicked the button.");
        }
    </script>

</body>
</html>
