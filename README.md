<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Smart Agriculture Startup</title>
<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@latest"></script>

<style>
body { font-family: Arial; margin:0; background:#eef5f1; }
header { background:#1b5e20; color:white; padding:20px; text-align:center; }
nav { background:#2e7d32; padding:10px; text-align:center; }
nav a { color:white; margin:10px; text-decoration:none; font-weight:bold; }
section { padding:20px; text-align:center; }
video, img { width:300px; border-radius:10px; margin-top:10px; }
button { padding:10px 15px; margin:10px; background:#2e7d32; color:white; border:none; border-radius:5px; }
.card { background:white; padding:15px; margin:15px auto; border-radius:10px; width:80%; box-shadow:0 2px 5px rgba(0,0,0,0.1);} 
</style>
</head>
<body>

<header>
<h1>🌱 AgriAI Startup Platform</h1>
<p>AI + IoT + Data for Smart Farming</p>
</header>

<nav>
<a href="#scan">Scan</a>
<a href="#weather">Weather</a>
<a href="#market">Market</a>
<a href="#dashboard">Dashboard</a>
</nav>

<section id="scan">
<h2>📷 AI Plant Scanner</h2>
<video id="camera" autoplay></video><br>
<button onclick="startCamera()">Start Camera</button>
<button onclick="captureImage()">Scan</button>
<canvas id="canvas" style="display:none"></canvas>
<p id="result"></p>
</section>

<section id="weather">
<h2>🌦️ Weather Advisory</h2>
<div class="card">
<p id="weatherData">Click below to get weather advice</p>
<button onclick="getWeather()">Get Weather Advice</button>
</div>
</section>

<section id="market">
<h2>💰 Market Price Prediction</h2>
<div class="card">
<select id="crop">
<option>Wheat</option>
<option>Rice</option>
<option>Maize</option>
</select><br>
<button onclick="predictPrice()">Predict Price</button>
<p id="priceResult"></p>
</div>
</section>

<section id="dashboard">
<h2>📊 Farmer Dashboard</h2>
<div class="card">
<p>Water Usage: 40% 💧</p>
<p>Soil Health: Good 🌱</p>
<p>Crop Status: Healthy ✅</p>
</div>
</section>

<script>
function startCamera() {
  navigator.mediaDevices.getUserMedia({ video: true })
  .then(stream => {
    document.getElementById('camera').srcObject = stream;
  });
}

function captureImage() {
  document.getElementById("result").innerText =
  "Detected: Leaf Disease → Use Neem Oil + Remove affected leaves";
}

function getWeather() {
  document.getElementById("weatherData").innerText =
  "Weather: Sunny ☀️\nAdvice: Irrigate crops today 💧";
}

function predictPrice() {
  const crop = document.getElementById("crop").value;
  document.getElementById("priceResult").innerText =
  crop + " Price Prediction: ₹2000/quintal (Expected ↑)";
}
</script>

</body>
</html>
