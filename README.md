<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>حاسبة بسيطة</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
        }
        #calculator {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            text-align: right;
            font-size: 20px;
        }
        button {
            width: 23%;
            padding: 10px;
            margin: 1%;
            font-size: 20px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="calculator">
        <input type="text" id="result" disabled>
        <div>
            <button onclick="appendToResult('1')">1</button>
            <button onclick="appendToResult('2')">2</button>
            <button onclick="appendToResult('3')">3</button>
            <button onclick="appendToResult('+')">+</button>
        </div>
        <div>
            <button onclick="appendToResult('4')">4</button>
            <button onclick="appendToResult('5')">5</button>
            <button onclick="appendToResult('6')">6</button>
            <button onclick="appendToResult('-')">-</button>
        </div>
        <div>
            <button onclick="appendToResult('7')">7</button>
            <button onclick="appendToResult('8')">8</button>
            <button onclick="appendToResult('9')">9</button>
            <button onclick="appendToResult('*')">*</button>
        </div>
        <div>
            <button onclick="clearResult()">C</button>
            <button onclick="appendToResult('0')">0</button>
            <button onclick="calculateResult()">=</button>
            <button onclick="appendToResult('/')">/</button>
        </div>
    </div>

    <script>
        function appendToResult(value) {
            document.getElementById('result').value += value;
        }

        function clearResult() {
            document.getElementById('result').value = '';
        }

        function calculateResult() {
            try {
                document.getElementById('result').value = eval(document.getElementById('result').value);
            } catch {
                document.getElementById('result').value = 'خطأ';
            }
        }
    </script>
</body>
</html>
