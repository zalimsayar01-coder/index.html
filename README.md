<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>For My Valentine ❤️</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body {
            display: flex; flex-direction: column; justify-content: center; align-items: center;
            height: 100vh; background: linear-gradient(135deg, #ffafbd, #ffc3a0);
            font-family: 'Poppins', sans-serif; overflow: hidden; text-align: center;
        }
        /* Floating Hearts Animation */
        .heart {
            position: absolute; color: rgba(255, 255, 255, 0.5);
            animation: float 5s infinite linear; z-index: 0;
        }
        @keyframes float {
            0% { transform: translateY(100vh) scale(0); opacity: 1; }
            100% { transform: translateY(-10vh) scale(1.5); opacity: 0; }
        }
        .container {
            width: 85%; max-width: 380px; padding: 30px;
            background: rgba(255, 255, 255, 0.9); border-radius: 30px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2); z-index: 10;
        }
        img { width: 100%; max-width: 200px; border-radius: 20px; margin-bottom: 15px; }
        h1 { color: #d63384; font-size: 1.4rem; margin-bottom: 20px; transition: 0.3s; }
        .buttons {
            display: flex; justify-content: center; align-items: center; 
            gap: 15px; position: relative; height: 80px;
        }
        button {
            padding: 15px 30px; font-size: 1.1rem; border: none;
            border-radius: 50px; cursor: pointer; font-weight: bold;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
        #yesBtn { background: #ff4d6d; color: white; transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        #noBtn {
