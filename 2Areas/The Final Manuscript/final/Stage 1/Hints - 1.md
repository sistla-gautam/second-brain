![[hints - 1 1.png]]

---
The hints are in the order of lowest to highest
1. Pay close attention to what the Manuscript is saying
2. Cross reference the evidence and the suspect list to find anything that catches your eye.
3. The medication bottle was said to be issued to Eleanor. Who might have prescribed it to her
---
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hint System</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
        }
        .hint-container {
            margin-top: 20px;
        }
        button {
            margin: 10px;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
        .dialog {
            display: none;
            position: fixed;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 20px;
            border: 1px solid black;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
        }
    </style>
</head>
<body>
    <h1>Mystery Hint System</h1>

  <h2>The hints are in the order of lowest to highest. Hint 1 is the least informative and Hint 3 is the most.</h2>
    
    <div class="hint-container">
        <button onclick="showHint('hint1')">Hint 1</button>
        <button onclick="showHint('hint2')">Hint 2</button>
        <button onclick="showHint('hint3')">Hint 3</button>
    </div>
    
    <div id="hint1" class="dialog">
        <p>Pay close attention to what the Manuscript is saying</p>
        <button onclick="closeHint('hint1')">Close</button>
    </div>
    
    <div id="hint2" class="dialog">
        <p>Cross reference the evidence and the suspect list to find anything that catches your eye.</p>
        <button onclick="closeHint('hint2')">Close</button>
    </div>
    
    <div id="hint3" class="dialog">
        <p>The medication bottle was said to be issued to Eleanor. Who might have prescribed it to her?</p>
        <button onclick="closeHint('hint3')">Close</button>
    </div>
    
    <script>
        function showHint(id) {
            document.getElementById(id).style.display = 'block';
        }
        function closeHint(id) {
            document.getElementById(id).style.display = 'none';
        }
    </script>
</body>
</html>

```