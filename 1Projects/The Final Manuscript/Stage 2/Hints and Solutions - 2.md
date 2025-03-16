# Hints
---
1. A-B-C-D-E-F
2. The calendar seems to have some numbers. Maybe they actually do mean something. Might it link to the financial records?
---
```HTML
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

    <h2>The hints are in the order of lowest to highest. Hint 1 is the least informative and Hint 2 is the most.</h2>

    <div class="hint-container">
        <button onclick="showHint('hint1')">Hint 1</button>
        <button onclick="showHint('hint2')">Hint 2</button>
    </div>

    <div id="hint1" class="dialog">
        <p>A-B-C-D-E-F</p>
        <button onclick="closeHint('hint1')">Close</button>
    </div>

    <div id="hint2" class="dialog">
        <p>The calendar seems to have some numbers. Maybe they actually do mean something. Might it link to the financial records?</p>
        <button onclick="closeHint('hint2')">Close</button>
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
---
# Solution

**STAGE 2 COMPLETION CARD**

**Case Status:** INVESTIGATION DEEPENING

**Key Findings:**  
✅ Eleanor was poisoned with **Diazepam** and **Amobarbital** — the latter was not prescribed.    
✅ A voicemail was **deleted remotely** after Eleanor's death — someone knew what she had discovered.  
✅ The manuscript was likely a blueprint for the murder — it implicates both financial and pharmaceutical ties.

**Confirmed Evidence:**

- **Voicemail Recording** — Eleanor's warning cut off moments before her death.
- **Bookmark Note** — Chemical formula and coded message suggest deeper conspiracy.
- **Matchstick** — Matches brand used by Henry Dawson, despite Eleanor’s smoking ban.
- **Wine Bottle** — Linked to Daniel Brooks; possible chemical traces found.

**Next Steps:**  
🔍 **Find out the hidden motives and the true suspects of the murder of Eleanor Blackwood.**