<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Question Page</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #ffd1dc, #ffe4e1);
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    .container {
      text-align: center;
      background: white;
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.1);
      position: relative;
    }

    h1 {
      margin-bottom: 30px;
    }

    .btn {
      padding: 12px 30px;
      font-size: 18px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      margin: 10px;
      transition: transform 0.2s ease;
    }

    .yes {
      background-color: #ff69b4;
      color: white;
    }

    .no {
      background-color: #aaa;
      color: white;
      position: absolute;
    }

    .success {
      display: none;
      font-size: 28px;
      color: #ff1493;
      margin-top: 20px;
    }

    .emoji {
      font-size: 40px;
      animation: float 2s infinite ease-in-out alternate;
    }

    @keyframes float {
      from { transform: translateY(0px); }
      to { transform: translateY(-20px); }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Do you like me? ❤️</h1>
    <button class="btn yes" onclick="sayYes()">Yes</button>
    <button class="btn no" id="noBtn">No</button>

    <div class="success" id="successMsg">
      <div class="emoji">🌸 💖 🌸 💕 🌸</div>
      <p>Yayyyy! You made my day! 💖</p>
    </div>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const container = document.querySelector(".container");

    noBtn.addEventListener("mouseenter", () => {
      moveButton();
    });

    function moveButton() {
      const containerRect = container.getBoundingClientRect();
      const maxX = containerRect.width - 100;
      const maxY = containerRect.height - 50;

      const randomX = Math.random() * maxX;
      const randomY = Math.random() * maxY;

      noBtn.style.left = randomX + "px";
      noBtn.style.top = randomY + "px";
    }

    function sayYes() {
      document.getElementById("successMsg").style.display = "block";
    }
  </script>
</body>
</html>
