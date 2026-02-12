<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            display: flex; flex-direction: column; justify-content: center; align-items: center;
            height: 100vh; background-color: #ffdae0; font-family: 'Arial', sans-serif;
            margin: 0; overflow: hidden; text-align: center;
        }
        .container {
            padding: 20px; transition: 0.3s;
        }
        img {
            width: 250px; height: 250px; object-fit: cover;
            border-radius: 20px; margin-bottom: 20px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        h1 { color: #d63384; font-size: 2rem; margin-bottom: 30px; }
        .buttons {
            display: flex; justify-content: center; align-items: center; gap: 20px;
        }
        button {
            padding: 15px 30px; font-size: 1.2rem; border: none;
            border-radius: 10px; cursor: pointer; font-weight: bold; transition: 0.2s;
        }
        #yesBtn { background-color: #28a745; color: white; }
        #noBtn { background-color: #dc3545; color: white; position: relative; }
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

        // Video ke dialogues aur images
        const dialogues = [
            "Are you sure?", 
            "Really sure??", 
            "Please don't do this to me :(", 
            "I'm gonna cry...", 
            "You are breaking my heart 💔",
            "I am very sad...",
            "I am very very sad..."
        ];
        
        const images = [
            "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNmN3YnF3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/OPU6wUKARAawgr6hlR/giphy.gif", // Crying
            "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOXp1eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/Tpsu9shpA7rW/giphy.gif", // Sad cat
            "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOGp1eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/d2lcHJTG5Tscg/giphy.gif" // Sobbing
        ];

        let clickCount = 0;

        noBtn.addEventListener("click", () => {
            if (clickCount < dialogues.length) {
                // Text badalna
                question.innerHTML = dialogues[clickCount];
                
                // Image badalna
                gif.src = images[clickCount % images.length];
                
                // Yes button ka size bada karna (Video effect)
                let currentSize = parseFloat(window.getComputedStyle(yesBtn).fontSize);
                yesBtn.style.fontSize = (currentSize + 15) + "px";
                yesBtn.style.padding = (currentSize) + "px " + (currentSize * 2) + "px";
                
                clickCount++;
            } else {
                // Jab dialogues khatam ho jayein toh No button bhagne lage
                moveNoButton();
            }
        });

        // No button ko bhagane wala function
        function moveNoButton() {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            noBtn.style.position = "absolute";
            noBtn.style.left = x + "px";
            noBtn.style.top = y + "px";
        }

        noBtn.addEventListener("mouseover", () => {
            if (clickCount >= dialogues.length) {
                moveNoButton();
            }
        });

        // Yes par click hone par
        yesBtn.addEventListener("click", () => {
            question.innerHTML = "Hehe! I knew it! ❤️😘";
            gif.src = "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHp1eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/K676643p5I7rLREe3F/giphy.gif";
            noBtn.style.display = "none";
            yesBtn.style.fontSize = "1.5rem";
            yesBtn.style.padding = "15px 30px";
        });
    </script>
</body>
</html>
