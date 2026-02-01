<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Love Page</title>

  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #ffe6ea;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .container {
      text-align: center;
    }

    img {
      width: 200px;
      margin-bottom: 20px;
    }

    h1 {
      font-size: 32px;
      margin-bottom: 20px;
    }

    button {
      padding: 12px 25px;
      font-size: 18px;
      border: none;
      border-radius: 20px;
      cursor: pointer;
      margin: 10px;
    }

    .yes {
      background-color: #ff5c8d;
      color: white;
    }

    .no {
      background-color: #ff8fab;
      color: white;
      position: absolute;
    }

    /* SECOND SCREEN */
    #secondScreen {
      display: none;
      background: #ffcc80;
      width: 100%;
      height: 100%;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }

    #secondScreen h1 {
      font-size: 60px;
      color: purple;
      animation: pop 1s infinite alternate;
    }

    @keyframes pop {
      from { transform: scale(1); }
      to { transform: scale(1.1); }
    }
  </style>
</head>

<body>

  <!-- FIRST SCREEN -->
  <div class="container" id="firstScreen">
    <img src="https://i.imgur.com/9YQZ6kT.png" alt="cute image">
    <h1>Do you love me?</h1>
    <button class="yes" onclick="showLove()">Yes</button>
    <button class="no" id="noBtn">No</button>
  </div>

  <!-- SECOND SCREEN -->
  <div class="container" id="secondScreen">
    <h1>I LOVE YOU 😍</h1>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");

    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 50);
      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    });

    function showLove() {
      document.getElementById("firstScreen").style.display = "none";
      document.getElementById("secondScreen").style.display = "flex";
    }
  </script>

</body>
</html>
