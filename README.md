<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Love Page</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #ffe6eb;
      font-family: Arial, sans-serif;
    }

    .questionContainer {
      position: relative;
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

    #yesBtn {
      background-color: #ff4d6d;
      color: white;
    }

    #noBtn {
      background-color: #ff8fab;
      color: white;
      position: absolute;
    }

    /* Loader */
    #heartLoader {
      display: none;
      font-size: 40px;
      animation: pulse 1s infinite;
    }

    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }

    /* Result screen */
    #resultContainer {
      display: none;
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

  <div class="questionContainer" id="questionContainer">
    <img src="images/love.png" alt="Love Image">
    <h1>Do you love me?</h1>

    <button id="yesBtn">Yes</button>
    <button id="noBtn">No</button>

    <div id="heartLoader">❤️</div>
    <div id="resultContainer">I LOVE YOU 😍</div>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const questionContainer = document.getElementById("questionContainer");
    const heartLoader = document.getElementById("heartLoader");
    const resultContainer = document.getElementById("resultContainer");

    // NO button runs away
    noBtn.addEventListener("mouseover", () => {
      const newX = Math.floor(Math.random() * 250);
      const newY = Math.floor(Math.random() * 150);

      noBtn.style.left = newX + "px";
      noBtn.style.top = newY + "px";
    });

    // YES button click
    yesBtn.addEventListener("click", () => {
      yesBtn.style.display = "none";
      noBtn.style.display = "none";
      heartLoader.style.display = "block";

      setTimeout(() => {
        heartLoader.style.display = "none";
        resultContainer.style.display = "block";
      }, 3000);
    });
  </script>

</body>
</html>
