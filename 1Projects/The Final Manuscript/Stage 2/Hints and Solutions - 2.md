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

**Case Status:** FURTHER INVESTIGATION COMPLETE

**Key Findings:**
✅ There is a hidden motive behind the murderers
✅ Eleanor seems to be trying to reveal something.

**New Developments:**

- The murder appears to involve **more than one person**.
- Some alibis don’t hold up under scrutiny.
- A missing voicemail may contain crucial information.

**Next Steps:**
🔍 **Deepen the investigation—more suspects and evidence unlocked!**  
🔍 **Identify possible connections between financial and medical records.**