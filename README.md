<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffe6e6;
            font-family: 'Arial', sans-serif;
            text-align: center;
            overflow: hidden;
        }
        .container {
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        h1 { color: #d63384; }
        .buttons {
            margin-top: 20px;
            position: relative;
        }
        button {
            font-size: 1.2rem;
            padding: 10px 25px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: 0.3s;
        }
        #yesBtn { background-color: #28a745; color: white; margin-right: 10px; }
        #noBtn { background-color: #dc3545; color: white; position: absolute; }
        img { width: 150px; border-radius: 10px; }
    </style>
</head>
<body>

    <div class="container">
        <img id="gif" src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHp1eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/K676643p5I7rLREe3F/giphy.gif" alt="cute cat">
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

        // No button move karne ka logic
        noBtn.addEventListener("mouseover", () => {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            noBtn.style.left = `${x}px`;
            noBtn.style.top = `${y}px`;
        });

        // Yes button click hone par logic
        yesBtn.addEventListener("click", () => {
            question.innerHTML = "Yayyy! I Love You! ❤️";
            gif.src = "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExN3RycXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4YnY5bmZ3Z3R4eXp3Ynd4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/v4aDR0YV1uC635fR39/giphy.gif";
            noBtn.style.display = "none";
        });
    </script>

</body>
</html>
