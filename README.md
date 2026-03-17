<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ishaq Dad | Portfolio</title>

<style>
body {
  margin: 0;
  font-family: 'Courier New', monospace;
  background: black;
  color: #00ffcc;
  overflow-x: hidden;
}

/* Matrix Rain */
canvas {
  position: fixed;
  top: 0;
  left: 0;
  z-index: -1;
}

.container {
  text-align: center;
  padding: 50px;
}

h1 {
  font-size: 3rem;
}

.glow {
  text-shadow: 0 0 10px #00ffcc;
}

.section {
  margin-top: 50px;
}

.card {
  border: 1px solid #00ffcc;
  padding: 20px;
  margin: 20px auto;
  width: 80%;
  border-radius: 10px;
  box-shadow: 0 0 15px #00ffcc;
}

button {
  background: black;
  color: #00ffcc;
  border: 1px solid #00ffcc;
  padding: 10px 20px;
  cursor: pointer;
}

button:hover {
  background: #00ffcc;
  color: black;
}

/* Terminal */
#terminal {
  background: black;
  border: 1px solid #00ffcc;
  padding: 20px;
  width: 80%;
  margin: auto;
  text-align: left;
  height: 200px;
  overflow-y: auto;
}
</style>
</head>
<body>

<canvas id="matrix"></canvas>

<div class="container">
  <h1 class="glow">🚀 Ishaq Dad</h1>
  <h3>Game Developer | CS Student | Future Security Engineer</h3>

  <div class="section card">
    <h2>👨‍💻 About Me</h2>
    <p>2nd Year Computer Science Student</p>
    <p>Game Developer working on <b>Last Horizon</b></p>
    <p>Learning Web Development & Programming</p>
    <p>Exploring Cybersecurity</p>
  </div>

  <div class="section card">
    <h2>🎮 Project</h2>
    <p><b>Last Horizon</b> - Game in progress</p>
  </div>

  <div class="section card">
    <h2>🧠 Skills</h2>
    <p>JavaScript | Python | HTML | C++ | C#</p>
  </div>

  <div class="section card">
    <h2>💻 Hacker Terminal</h2>
    <div id="terminal"></div>
    <button onclick="runTerminal()">Run</button>
  </div>
</div>

<script>
// MATRIX EFFECT
const canvas = document.getElementById('matrix');
const ctx = canvas.getContext('2d');
canvas.height = window.innerHeight;
canvas.width = window.innerWidth;

const letters = "01";
const fontSize = 14;
const columns = canvas.width / fontSize;

const drops = [];
for (let x = 0; x < columns; x++) drops[x] = 1;

function draw() {
  ctx.fillStyle = "rgba(0,0,0,0.05)";
  ctx.fillRect(0, 0, canvas.width, canvas.height);
  ctx.fillStyle = "#0f0";
  ctx.font = fontSize + "px monospace";

  for (let i = 0; i < drops.length; i++) {
    const text = letters[Math.floor(Math.random() * letters.length)];
    ctx.fillText(text, i * fontSize, drops[i] * fontSize);

    if (drops[i] * fontSize > canvas.height && Math.random() > 0.975)
      drops[i] = 0;

    drops[i]++;
  }
}
setInterval(draw, 33);

// TERMINAL EFFECT
const terminal = document.getElementById("terminal");
const commands = [
  "Initializing system...",
  "Loading skills...",
  "JavaScript ✔",
  "Python ✔",
  "Cybersecurity module loading...",
  "Access Granted 🚀"
];

function runTerminal() {
  terminal.innerHTML = "";
  let i = 0;

  const interval = setInterval(() => {
    if (i < commands.length) {
      terminal.innerHTML += commands[i] + "<br>";
      i++;
      terminal.scrollTop = terminal.scrollHeight;
    } else {
      clearInterval(interval);
    }
  }, 500);
}
</script>

</body>
</html>
