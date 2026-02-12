<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Will You Be My Valentine? ❤️</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        
        body {
            display: flex; flex-direction: column; justify-content: center; align-items: center;
            height: 100vh; background-color: #ffdae0; font-family: 'Arial', sans-serif;
            overflow: hidden; text-align: center; padding: 20px;
        }

        .container {
            width: 100%; max-width: 400px; padding: 20px;
            background: white; border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        img {
            width: 100%; max-width: 220px; height: auto;
            border-radius: 15px; margin-bottom: 20px;
        }

        h1 { color: #d63384; font-size: 1.5rem; margin-bottom: 25px; min-height: 60px; }

        .buttons {
            display: flex; justify-content: center; align-items: center; 
            gap: 15px; position: relative; width: 100%; height: 60px;
        }

        button {
            padding: 12px 25px; font-size: 1rem; border: none;
            border-radius: 10px; cursor: pointer; font-weight: bold;
            transition: 0.2s ease; touch-action: manipulation;
        }

        #yesBtn { background-color: #28a745; color: white; z-index: 2; }
        
        #noBtn { 
            background-color: #dc3545; color: white; 
            position: absolute; white-space: nowrap; z-index: 1;
        }
    </style>
</head>
<body>

    <div class="container">
        <img id="gif" src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHp1eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/K676643p5I7rLREe3F/giphy.gif" alt="Asking">
        
        <h1 id="question">Will you be my Valentine? ❤️</h1>
        
        <div class="buttons">
            <button id="yesBtn">Yes</button>
            <button id="noBtn">No</button>
        </div>
    </div>

    <script>
        const noBtn = document.getElementById("noBtn");
        const yesBtn = document.getElementById("yesBtn");
        const question = document.getElementById("question");
        const gif = document.getElementById("gif");

        const dialogues = [
            "Are you sure?", "Really sure??", "Please...", "I'll cry... :(", 
            "Breaking my heart 💔", "I'm very sad...", "Plzzzzzz 😭"
        ];
        
        const images = [
            "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNmN3YnF3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/OPU6wUKARAawgr6hlR/giphy.gif",
            "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOXp1eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/Tpsu9shpA7rW/giphy.gif",
            "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOGp1eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/d2lcHJTG5Tscg/giphy.gif"
        ];

        let clickCount = 0;

        function handleNoInteraction() {
            if (clickCount < dialogues.length) {
                question.innerHTML = dialogues[clickCount];
                gif.src = images[clickCount % images.length];
                
                // Yes button gets bigger
                let currentSize = parseFloat(window.getComputedStyle(yesBtn).fontSize);
                yesBtn.style.fontSize = (currentSize + 10) + "px";
                yesBtn.style.padding = (currentSize) + "px " + (currentSize * 1.5) + "px";
                
                clickCount++;
            } else {
                moveNoButton();
            }
        }

        function moveNoButton() {
            // Mobile safe area (taki button screen ke bahar na jaye)
            const padding = 50;
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth - padding);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight - padding);
            
            noBtn.style.position = "fixed"; 
            noBtn.style.left = Math.max(padding, x) + "px";
            noBtn.style.top = Math.max(padding, y) + "px";
        }

        // Mobile touch and PC mouse events
        noBtn.addEventListener("touchstart", (e) => {
            e.preventDefault(); // Prevents clicking
            handleNoInteraction();
        });

        noBtn.addEventListener("mouseover", () => {
            if (clickCount >= dialogues.length) moveNoButton();
        });

        noBtn.addEventListener("click", handleNoInteraction);

        yesBtn.addEventListener("click", () => {
            question.innerHTML = "Yayyy! I knew it! ❤️😘";
            gif.src = "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHp1eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/K676643p5I7rLREe3F/giphy.gif";
            noBtn.style.display = "none";
        });
    </script>
</body>
</html>
