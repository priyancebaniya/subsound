<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Subsound — Where Music Becomes Visible</title>

<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">

<style>
body {
  margin: 0;
  font-family: DM Sans, sans-serif;
  background: #fafaf8;
  color: #0e0e0e;
}

nav {
  display: flex;
  justify-content: space-between;
  padding: 20px 40px;
  border-bottom: 1px solid #ddd;
}

.logo {
  font-family: "Instrument Serif", serif;
  font-size: 20px;
}

.hero {
  text-align: center;
  padding: 80px 20px;
}

.hero h1 {
  font-family: "Instrument Serif", serif;
  font-size: 48px;
  margin-bottom: 10px;
}

.hero p {
  color: #555;
}

input {
  padding: 12px;
  width: 60%;
  margin-top: 20px;
  border: 1px solid #000;
}

button {
  padding: 12px 18px;
  border: none;
  background: black;
  color: white;
  cursor: pointer;
}

.results {
  display: none;
  max-width: 800px;
  margin: auto;
  padding: 20px;
}

.card {
  border: 1px solid #ddd;
  padding: 15px;
  margin-top: 15px;
}

footer {
  text-align: center;
  padding: 30px;
  border-top: 1px solid #ddd;
  margin-top: 60px;
}
</style>
</head>

<body>

<nav>
  <div class="logo">Subsound</div>
  <div>Music × Neuroscience</div>
</nav>

<div class="hero">
  <h1>What does music do to your brain?</h1>
  <p>Analyze songs through neuroscience.</p>

  <input id="songInput" placeholder="Enter song name..." />
  <button onclick="analyse()">Analyse</button>
</div>

<div class="results" id="results"></div>

<footer>
  Subsound · Built for neuroscience music exploration
</footer>

<script>
function analyse() {
  const input = document.getElementById("songInput").value;
  const results = document.getElementById("results");

  if (!input) return;

  results.style.display = "block";

  results.innerHTML = `
    <div class="card">
      <h3>${input}</h3>
      <p>Brain response analysis loaded (demo mode).</p>
    </div>
  `;
}
</script>

</body>
</html>
