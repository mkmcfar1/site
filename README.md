# site

<DOCTYPE html>
<html>
<head>

<h1>Thomasson Family Game Collection</h1>

<script src="https://cdn.jsdelivr.net/npm/xlsx/dist/xlsx.full.min.js"></script>

<DOCTYPE html>
<html>
<head>
    <title>Thomasson Family Game Collection</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background-color: #ffffff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            text-align: center;
            max-width: 400px;
            width: 100%;
        }

        h1 {
            color: #333333;
            font-size: 24px;
        }

        input[type="file"], input[type="text"] {
            display: block;
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 14px;
        }

        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
        }

        button:hover {
            background-color: #45a049;
        }

        .output {
            margin-top: 20px;
            font-size: 14px;
            color: #666666;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Thomasson Family Game Collection</h1>
        <form id="fileForm">
            <input type="file" id="uploadFile" accept=".xlsx, .xls">
            <input type="text" id="newName" placeholder="Enter a new game title">
            <button type="button" onclick="modifyExcel()">Modify Excel</button>
        </form>
        <div id="output" class="output"></div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/xlsx/dist/xlsx.full.min.js"></script>
    <script>
        // JavaScript logic remains unchanged
    </script>
</body>
</html>

@media (max-width: 600px) {
    .container {
        width: 90%;
        padding: 10px;
    }

    h1 {
        font-size: 20px;
    }
}

