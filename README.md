<img align="right" src="https://visitor-badge.laobi.icu/badge?page_id=dawissem.dawissem" />

<h1 align="center">
    <img src="https://readme-typing-svg.herokuapp.com/?font=Righteous&size=35&center=true&vCenter=true&width=500&height=70&duration=4000&lines=Hi+There!+👋;+I'm+Wissem!;Full+Stack+Developer;AI+%26+ML+Enthusiast;Welcome+to+my+Profile!" />
</h1>

<h3 align="center">🚀 Passionate Full Stack Developer | AI/ML Engineer | Problem Solver | Tech Enthusiast 🚀</h3>

<div align="center">
  <img src="https://media.giphy.com/media/dWesBcTLavkZuG35MI/giphy.gif" width="600" height="300"/>
</div>

---

## 🙋‍♂️ About Me

<img align="right" alt="Coding" width="400" src="https://media.giphy.com/media/SWoSkN6DxTszqIKEqv/giphy.gif">

- 🔭 Currently working on **E-commerce Platform with Microservices Architecture & AI Integration**
- 🌱 Learning **Docker, DevOps, Kubernetes & Cloud Technologies**
- 🤖 Exploring **Machine Learning, Deep Learning & AI Applications**
- 👯 Looking to collaborate on **Open Source Projects & AI/ML Solutions**
- 💬 Ask me about **Java, Spring Boot, Django, Angular, React, Python, AI/ML**
- 📫 How to reach me: **dawissem.wm@gmail.com**
- ⚡ Fun fact: **Code is poetry in motion! 🎭**
- 🎯 Goal: **To build impactful software solutions powered by AI**

---

## 🛠️ Tech Stack & Tools

### Languages
<div align="center">
    <img src="https://skillicons.dev/icons?i=java,python,javascript,typescript,php,c,html,css" />
</div>

### Frameworks & Libraries
<div align="center">
    <img src="https://skillicons.dev/icons?i=spring,django,nodejs,react,angular,bootstrap,android" />
</div>

### AI/ML & Data Science
<div align="center">
    <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" />
    <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" />
    <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />
    <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
    <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
    <img src="https://img.shields.io/badge/OpenCV-27338e?style=for-the-badge&logo=OpenCV&logoColor=white" />
    <img src="https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=Keras&logoColor=white" />
    <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=Jupyter&logoColor=white" />
</div>

### Databases & Cloud
<div align="center">
    <img src="https://skillicons.dev/icons?i=mysql,mongodb,firebase,postgres" />
</div>

### Tools & Technologies
<div align="center">
    <img src="https://skillicons.dev/icons?i=docker,git,github,vscode,figma,postman,linux" />
</div>

---

## 📊 GitHub Analytics

<div align="center">
  <img height="180em" src="https://github-readme-stats-eight-theta.vercel.app/api?username=dawissem&show_icons=true&theme=algolia&include_all_commits=true&count_private=true"/>
  <img height="180em" src="https://github-readme-stats-eight-theta.vercel.app/api/top-langs/?username=dawissem&layout=compact&langs_count=8&theme=algolia"/>
</div>

<div align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=dawissem&theme=algolia" alt="GitHub Streak" />
</div>

---

## 🏆 GitHub Trophies

<div align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=dawissem&theme=algolia&no-frame=true&no-bg=false&margin-w=4&row=1" />
</div>

---

## 🎮 Interactive Snake Game

<div align="center">
  <h3>🐍 Play Snake Game - Eat My Contributions! 🐍</h3>
  <p><em>Use arrow keys to control the snake</em></p>
</div>

<div align="center" id="snake-game-container">
  <canvas id="snakeCanvas" width="400" height="400" style="border: 2px solid #58a6ff; border-radius: 10px; background-color: #0d1117;"></canvas>
  <br>
  <div style="margin-top: 10px;">
    <span style="color: #58a6ff; font-weight: bold;">Score: <span id="score">0</span></span>
    <button onclick="restartGame()" style="margin-left: 20px; padding: 5px 10px; background-color: #58a6ff; color: white; border: none; border-radius: 5px; cursor: pointer;">Restart</button>
  </div>
</div>

<script>
const canvas = document.getElementById('snakeCanvas');
const ctx = canvas.getContext('2d');
const scoreElement = document.getElementById('score');

const gridSize = 20;
const tileCount = canvas.width / gridSize;

let snake = [
    {x: 10, y: 10}
];
let food = {};
let dx = 0;
let dy = 0;
let score = 0;

function generateFood() {
    food = {
        x: Math.floor(Math.random() * tileCount),
        y: Math.floor(Math.random() * tileCount)
    };
}

function drawGame() {
    clearCanvas();
    moveSnake();
    drawSnake();
    drawFood();
    checkCollision();
    updateScore();
}

function clearCanvas() {
    ctx.fillStyle = '#0d1117';
    ctx.fillRect(0, 0, canvas.width, canvas.height);
}

function drawSnake() {
    ctx.fillStyle = '#58a6ff';
    snake.forEach(segment => {
        ctx.fillRect(segment.x * gridSize, segment.y * gridSize, gridSize - 2, gridSize - 2);
    });
}

function drawFood() {
    ctx.fillStyle = '#f85149';
    ctx.fillRect(food.x * gridSize, food.y * gridSize, gridSize - 2, gridSize - 2);
}

function moveSnake() {
    const head = {x: snake[0].x + dx, y: snake[0].y + dy};
    snake.unshift(head);
    
    if (head.x === food.x && head.y === food.y) {
        score += 10;
        generateFood();
    } else {
        snake.pop();
    }
}

function checkCollision() {
    const head = snake[0];
    
    if (head.x < 0 || head.x >= tileCount || head.y < 0 || head.y >= tileCount) {
        resetGame();
    }
    
    for (let i = 1; i < snake.length; i++) {
        if (head.x === snake[i].x && head.y === snake[i].y) {
            resetGame();
        }
    }
}

function resetGame() {
    snake = [{x: 10, y: 10}];
    dx = 0;
    dy = 0;
    score = 0;
    generateFood();
}

function restartGame() {
    resetGame();
}

function updateScore() {
    scoreElement.textContent = score;
}

document.addEventListener('keydown', (e) => {
    if (e.key === 'ArrowUp' && dy === 0) {
        dx = 0;
        dy = -1;
    } else if (e.key === 'ArrowDown' && dy === 0) {
        dx = 0;
        dy = 1;
    } else if (e.key === 'ArrowLeft' && dx === 0) {
        dx = -1;
        dy = 0;
    } else if (e.key === 'ArrowRight' && dx === 0) {
        dx = 1;
        dy = 0;
    }
});

generateFood();
setInterval(drawGame, 100);
</script>

---

## 📈 Contribution Graph

<div align="center">
  <img alt="snake eating my contributions" src="https://raw.githubusercontent.com/salesp07/salesp07/output/github-contribution-grid-snake.svg" />
</div>

---

## 🌟 Featured Projects

<div align="center">
  <a href="https://github.com/dawissem/ecommerce-project">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=dawissem&repo=ecommerce-project&theme=algolia" />
  </a>
  <a href="https://github.com/dawissem/android-app">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=dawissem&repo=android-app&theme=algolia" />
  </a>
</div>

---

## 🤖 AI/ML Projects Showcase

<div align="center">
  <a href="https://github.com/dawissem/ml-project">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=dawissem&repo=ml-project&theme=algolia" />
  </a>
  <a href="https://github.com/dawissem/ai-chatbot">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=dawissem&repo=ai-chatbot&theme=algolia" />
  </a>
</div>

---

## 📫 Connect With Me

<div align="center">
  <a href="mailto:dawissem.wm@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-333333?style=for-the-badge&logo=gmail&logoColor=red" />
  </a>
  <a href="https://www.linkedin.com/in/wissem-manai-553313141/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="https://github.com/dawissem" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" />
  </a>
  <a href="https://twitter.com/your_twitter" target="_blank">
    <img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" />
  </a>
  <a href="https://www.kaggle.com/wissem" target="_blank">
    <img src="https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=Kaggle&logoColor=white" />
  </a>
</div>

---

## 💡 Quote of the Day

<div align="center">
  <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=algolia" />
</div>

---

## 🎵 Currently Listening To

<div align="center">
  <img src="https://spotify-github-profile.vercel.app/api/spotify?background_color=0d1117&border_color=ffffff" />
</div>

---

<div align="center">
  <h3>🚀 Let's Build Something Amazing Together! 🚀</h3>
  <p>
    <img src="https://komarev.com/ghpvc/?username=dawissem&label=Profile%20views&color=0e75b6&style=flat" alt="Profile views" />
  </p>
</div>

---

<div align="center">
  <img src="https://media.giphy.com/media/LnQjpWaON8nhr21vNW/giphy.gif" width="60"> 
  <em><b>I love connecting with different people</b> so if you want to say <b>hi, I'll be happy to meet you more!</b> 😊</em>
</div>
