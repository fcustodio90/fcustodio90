# 👋 Hi, I'm Filipe Custódio

## About Me

- 🔭 Software Developer && Chartered Accountant
- 🌱 Passionate about Ruby on Rails and building scalable applications

## Tech Stack

- 💻 Languages: Ruby, JavaScript
- 🛠️ Tools & Technologies:
  - Ruby on Rails
  - PostgreSQL
  - Redis
  - Docker
  - Git
- 🌐 Frameworks:
  - Rails
  - React
  - Vue

## Current Projects

- 🏥 Building innovative solutions for pharmaceutical retail
- Developing loyalty and promotion systems

## GitHub Stats & Activity

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=fcustodio90&theme=radical)

## Top Languages

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=fcustodio90&layout=compact&theme=radical)

## 🎮 Play Snake Game!

<details>
<summary>Click to play! 🐍</summary>

```html
<div align="center">
  <canvas
    id="gameCanvas"
    width="400"
    height="400"
    style="border:2px solid #2ea44f;"
  ></canvas>
  <br />
  <button
    onclick="startGame()"
    style="background-color: #2ea44f; color: white; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer;"
  >
    Start Game
  </button>
  <p>Score: <span id="score">0</span></p>
  <p>Use arrow keys to move the snake!</p>
</div>

<script>
  let canvas = document.getElementById("gameCanvas")
  let ctx = canvas.getContext("2d")
  let snake = [{ x: 200, y: 200 }]
  let food = { x: 0, y: 0 }
  let dx = 10
  let dy = 0
  let score = 0
  let gameLoop

  function drawSnake() {
    ctx.fillStyle = "#2ea44f"
    snake.forEach((segment) => {
      ctx.fillRect(segment.x, segment.y, 10, 10)
    })
  }

  function drawFood() {
    ctx.fillStyle = "red"
    ctx.fillRect(food.x, food.y, 10, 10)
  }

  function moveSnake() {
    const head = { x: snake[0].x + dx, y: snake[0].y + dy }
    snake.unshift(head)
    if (head.x === food.x && head.y === food.y) {
      score += 10
      document.getElementById("score").textContent = score
      generateFood()
    } else {
      snake.pop()
    }
  }

  function generateFood() {
    food.x = Math.floor(Math.random() * 40) * 10
    food.y = Math.floor(Math.random() * 40) * 10
  }

  function gameOver() {
    clearInterval(gameLoop)
    ctx.fillStyle = "black"
    ctx.font = "30px Arial"
    ctx.fillText("Game Over!", 150, 200)
  }

  function startGame() {
    snake = [{ x: 200, y: 200 }]
    dx = 10
    dy = 0
    score = 0
    document.getElementById("score").textContent = score
    generateFood()
    if (gameLoop) clearInterval(gameLoop)
    gameLoop = setInterval(() => {
      ctx.clearRect(0, 0, canvas.width, canvas.height)
      moveSnake()
      drawSnake()
      drawFood()

      const head = snake[0]
      if (
        head.x < 0 ||
        head.x >= canvas.width ||
        head.y < 0 ||
        head.y >= canvas.height
      ) {
        gameOver()
      }

      for (let i = 1; i < snake.length; i++) {
        if (head.x === snake[i].x && head.y === snake[i].y) {
          gameOver()
        }
      }
    }, 100)
  }

  document.addEventListener("keydown", (e) => {
    switch (e.key) {
      case "ArrowUp":
        if (dy === 0) {
          dx = 0
          dy = -10
        }
        break
      case "ArrowDown":
        if (dy === 0) {
          dx = 0
          dy = 10
        }
        break
      case "ArrowLeft":
        if (dx === 0) {
          dx = -10
          dy = 0
        }
        break
      case "ArrowRight":
        if (dx === 0) {
          dx = 10
          dy = 0
        }
        break
    }
  })
</script>
```

</details>

## Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/filipe-custodio)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-lightgrey)](https://github.com/fcustodio90)
[![Visits](https://badges.pufler.dev/visits/fcustodio90/fcustodio90?color=blue&logo=github)](https://github.com/fcustodio90)
[![Years](https://badges.pufler.dev/years/fcustodio90?color=blue&logo=github)](https://github.com/fcustodio90)
[![Repos](https://badges.pufler.dev/repos/fcustodio90?color=blue&logo=github)](https://github.com/fcustodio90)

---

⭐️ From [fcustodio90](https://github.com/fcustodio90)

[![Made with Cursor](https://img.shields.io/badge/Made%20with-Cursor-2ea44f)](https://cursor.sh)
