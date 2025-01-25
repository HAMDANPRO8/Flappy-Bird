<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flappy Bird</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      background: #000;
    }

    #game-container {
      position: relative;
      width: 100%;
      height: 100%;
    }

    canvas {
      display: block;
      position: absolute;
      top: 0;
      left: 0;
    }
  </style>
</head>
<body>
  <div id="game-container">
    <canvas id="gameCanvas"></canvas>
  </div>
  <script>
    const canvas = document.getElementById("gameCanvas");
    const ctx = canvas.getContext("2d");

    // Canvas dimensions
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    // Game variables
    let birdX = 50;
    let birdY = 150;
    let birdVelocity = 0;
    const gravity = 0.4;
    const birdRadius = 10;
    const flapPower = -6;

    let pipes = [];
    const pipeWidth = 50;
    const pipeGap = 140;
    const pipeSpeedInitial = 2;
    let pipeSpeed = pipeSpeedInitial;
    const minGap = 50; // Minimum distance from screen edges

    let score = 0;
    let isGameOver = false;

    // Background image
    const background = new Image();
    background.src = "background.jpg"; // Replace with your image file
    background.onload = () => {
      createPipe();
      gameLoop();
    };
    background.onerror = () => {
      console.error("Background image failed to load.");
      gameLoop(); // Continue without background
    };

    // Sounds (placeholders)
    const flapSound = new Audio("flap.mp3"); // Add your sound file
    const hitSound = new Audio("hit.mp3"); // Add your sound file
    const scoreSound = new Audio("score.mp3"); // Add your sound file

    // Add pipes
    function createPipe() {
      const pipeHeight = Math.random() * (canvas.height - pipeGap - 2 * minGap) + minGap;
      pipes.push({
        x: canvas.width,
        top: pipeHeight,
        bottom: pipeHeight + pipeGap,
      });
    }

    // Draw bird (using an image now)
    const birdImage = new Image();
    birdImage.src = "bird.png"; // Ensure the path matches your project structure

    function drawBird() {
      ctx.drawImage(birdImage, birdX - birdRadius, birdY - birdRadius, birdRadius * 2, birdRadius * 2);
    }

    // Draw pipes
    function drawPipes() {
      pipes.forEach((pipe) => {
        // Top pipe
        const topPipeGradient = ctx.createLinearGradient(pipe.x, 0, pipe.x + pipeWidth, 0);
        topPipeGradient.addColorStop(0, "#228B22");
        topPipeGradient.addColorStop(1, "#32CD32");

        ctx.fillStyle = topPipeGradient;
        ctx.fillRect(pipe.x, 0, pipeWidth, pipe.top);

        ctx.fillStyle = "#006400";
        ctx.fillRect(pipe.x - 2, pipe.top - 10, pipeWidth + 4, 10); // Decorative top edge

        // Bottom pipe
        const bottomPipeGradient = ctx.createLinearGradient(pipe.x, pipe.bottom, pipe.x + pipeWidth, pipe.bottom);
        bottomPipeGradient.addColorStop(0, "#228B22");
        bottomPipeGradient.addColorStop(1, "#32CD32");

        ctx.fillStyle = bottomPipeGradient;
        ctx.fillRect(pipe.x, pipe.bottom, pipeWidth, canvas.height - pipe.bottom);

        ctx.fillStyle = "#006400";
        ctx.fillRect(pipe.x - 2, pipe.bottom, pipeWidth + 4, 10); // Decorative bottom edge
      });
    }

    // Update game objects
    function updateGame() {
      if (isGameOver) return;

      birdVelocity += gravity;
      birdY += birdVelocity;

      pipes.forEach((pipe) => {
        pipe.x -= pipeSpeed;

        // Check collision
        if (
          birdX + birdRadius > pipe.x &&
          birdX - birdRadius < pipe.x + pipeWidth &&
          (birdY - birdRadius < pipe.top || birdY + birdRadius > pipe.bottom)
        ) {
          isGameOver = true;
          hitSound.play();
        }

        // Check if pipe is off-screen
        if (pipe.x + pipeWidth < 0) {
          pipes.shift();
          score++;
          scoreSound.play();

          // Increase difficulty
          if (score % 5 === 0) {
            pipeSpeed += 0.2;
          }
        }
      });

      // Check if bird hits the ground or flies off-screen
      if (birdY + birdRadius > canvas.height || birdY - birdRadius < 0) {
        isGameOver = true;
        hitSound.play();
      }

      // Add new pipes
      if (pipes.length === 0 || pipes[pipes.length - 1].x < canvas.width - 200) {
        createPipe();
      }
    }

    // Draw game elements
    function drawGame() {
      // Draw background
      ctx.drawImage(background, 0, 0, canvas.width, canvas.height);

      drawPipes();
      drawBird();

      // Draw score
      ctx.fillStyle = "rgba(0, 0, 0, 0.5)";
      ctx.fillRect(5, 5, 100, 30);
      ctx.fillStyle = "white";
      ctx.font = "20px Arial";
      ctx.fillText(`Score: ${score}`, 10, 25);

      // Draw game over message
      if (isGameOver) {
        ctx.fillStyle = "red";
        ctx.font = "30px Arial";
        ctx.fillText("Game Over", canvas.width / 2 - 75, canvas.height / 2);
        ctx.fillStyle = "black";
        ctx.font = "15px Arial";
        ctx.fillText("Tap to Restart", canvas.width / 2 - 55, canvas.height / 2 + 30);
      }
    }

    // Main game loop
    function gameLoop() {
      updateGame();
      drawGame();
      if (!isGameOver) {
        requestAnimationFrame(gameLoop);
      }
    }

    // Handle bird flap
    function flap() {
      if (isGameOver) {
        birdY = 150;
        birdVelocity = 0;
        pipes = [];
        score = 0;
        pipeSpeed = pipeSpeedInitial;
        isGameOver = false;
        createPipe();
        gameLoop();
      } else {
        birdVelocity = flapPower;
        flapSound.play();
      }
    }

    // Input handlers
    canvas.addEventListener("click", flap);
    canvas.addEventListener("touchstart", flap);

    // Start game
    background.onload = () => {
      createPipe();
      gameLoop();
    };
  </script>
</body>
</html>
