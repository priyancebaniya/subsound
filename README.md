# subsound
Where music becomes visible through neuroscience.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Subsound — Where Music Becomes Visible</title>
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
:root {
  --black: #0e0e0e;
  --white: #fafaf8;
  --g100: #f0efeb;
  --g200: #e0dedb;
  --g300: #c8c6c0;
  --g500: #9a9890;
  --g700: #4a4844;
  --serif: 'Instrument Serif', Georgia, serif;
  --sans: 'DM Sans', sans-serif;
}
html { scroll-behavior: smooth; }
body { background: var(--white); color: var(--black); font-family: var(--sans); font-weight: 300; min-height: 100vh; }

/* NAV */
nav {
  display: flex; align-items: center; justify-content: space-between;
  padding: 1.4rem 3rem;
  border-bottom: 0.5px solid var(--g300);
  position: sticky; top: 0; z-index: 100;
  background: rgba(250,250,248,0.95);
  backdrop-filter: blur(10px);
}
.logo { font-family: var(--serif); font-size: 1.2rem; letter-spacing: -0.02em; }
.nav-tag { font-size: 0.72rem; letter-spacing: 0.1em; text-transform: uppercase; color: var(--g500); }

/* HERO */
.hero {
  padding: 5rem 3rem 3rem;
  max-width: 900px; margin: 0 auto;
  text-align: center;
}
.hero-label {
  font-size: 0.72rem; letter-spacing: 0.14em; text-transform: uppercase;
  color: var(--g500); margin-bottom: 1.5rem;
}
.hero-title {
  font-family: var(--serif);
  font-size: clamp(2.8rem, 6vw, 5.5rem);
  line-height: 1.05; letter-spacing: -0.03em;
  margin-bottom: 1.2rem;
}
.hero-title em { font-style: italic; color: var(--g500); }
.hero-sub {
  font-size: 1rem; color: var(--g700); line-height: 1.7;
  max-width: 420px; margin: 0 auto 2.5rem;
}

/* SEARCH */
.search-wrap {
  display: flex; max-width: 520px; margin: 0 auto;
  border: 1px solid var(--black);
}
.search-wrap input {
  flex: 1; padding: 0.9rem 1.2rem;
  font-family: var(--sans); font-size: 0.95rem; font-weight: 300;
  border: none; background: transparent; color: var(--black); outline: none;
}
.search-wrap input::placeholder { color: var(--g500); }
.search-wrap button {
  padding: 0.9rem 1.4rem;
  background: var(--black); color: var(--white);
  border: none; font-family: var(--sans);
  font-size: 0.75rem; letter-spacing: 0.08em; text-transform: uppercase;
  cursor: pointer; transition: opacity 0.2s; white-space: nowrap;
}
.search-wrap button:hover { opacity: 0.7; }
.search-wrap button:disabled { opacity: 0.4; cursor: not-allowed; }

/* WAVE */
.wave-row {
  display: flex; align-items: center; justify-content: center;
  gap: 3px; height: 48px; margin: 2.5rem auto; max-width: 400px;
}
.wbar {
  width: 2px; background: var(--g300); border-radius: 2px;
  transition: height 0.3s ease;
}
.wbar.active { background: var(--black); }

/* RESULTS */
.results { max-width: 860px; margin: 0 auto; padding: 0 3rem 5rem; }

.song-header {
  display: flex; align-items: flex-start; justify-content: space-between;
  padding: 2rem 0 1.5rem;
  border-bottom: 0.5px solid var(--g300);
  margin-bottom: 2.5rem;
  gap: 1rem;
}
.song-title { font-family: var(--serif); font-size: 2rem; letter-spacing: -0.02em; }
.song-artist { font-size: 0.9rem; color: var(--g500); margin-top: 0.3rem; }
.song-badge {
  font-size: 0.7rem; letter-spacing: 0.1em; text-transform: uppercase;
  border: 0.5px solid var(--g300); padding: 0.4rem 0.8rem;
  color: var(--g700); white-space: nowrap; flex-shrink: 0;
}

/* BRAIN SCAN */
.section-label {
  font-size: 0.7rem; letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--g500); margin-bottom: 1.2rem;
}
.brain-grid {
  display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1px; background: var(--g300); border: 0.5px solid var(--g300);
  margin-bottom: 2.5rem;
}
.brain-card {
  background: var(--white); padding: 1.5rem;
  transition: background 0.2s;
}
.brain-card:hover { background: var(--g100); }
.bc-metric { font-size: 0.68rem; letter-spacing: 0.1em; text-transform: uppercase; color: var(--g500); margin-bottom: 0.6rem; }
.bc-value {
  font-family: var(--serif); font-size: 2rem;
  letter-spacing: -0.02em; margin-bottom: 0.5rem; line-height: 1;
}
.bc-bar-track {
  height: 2px; background: var(--g200); margin-bottom: 0.8rem; border-radius: 2px;
}
.bc-bar-fill {
  height: 100%; background: var(--black); border-radius: 2px;
  transition: width 1s ease;
}
.bc-explain { font-size: 0.82rem; color: var(--g700); line-height: 1.6; }

/* FINGERPRINT */
.fingerprint-section {
  display: grid; grid-template-columns: 1fr 1fr; gap: 3rem;
  align-items: center; margin-bottom: 2.5rem;
}
@media (max-width: 600px) { .fingerprint-section { grid-template-columns: 1fr; } }
.fp-canvas-wrap {
  border: 0.5px solid var(--g300); background: var(--white);
  display: flex; align-items: center; justify-content: center;
  padding: 2rem; aspect-ratio: 1;
}
canvas#fpCanvas { width: 100%; height: 100%; max-width: 260px; max-height: 260px; }
.fp-legend h3 { font-family: var(--serif); font-size: 1.4rem; letter-spacing: -0.02em; margin-bottom: 1rem; }
.fp-legend p { font-size: 0.85rem; color: var(--g700); line-height: 1.7; margin-bottom: 1rem; }
.fp-tags { display: flex; flex-wrap: wrap; gap: 6px; }
.fp-tag {
  font-size: 0.7rem; letter-spacing: 0.08em; text-transform: uppercase;
  border: 0.5px solid var(--g300); padding: 0.3rem 0.7rem; color: var(--g700);
}

/* NARRATIVE */
.narrative-box {
  border: 0.5px solid var(--g300); padding: 2rem 2.5rem;
  margin-bottom: 2.5rem; background: var(--g100);
}
.narrative-box h3 {
  font-family: var(--serif); font-size: 1.1rem; margin-bottom: 1rem;
  letter-spacing: -0.01em;
}
.narrative-box p { font-size: 0.9rem; color: var(--g700); line-height: 1.8; }

/* LOADING */
.loading {
  display: none; text-align: center; padding: 4rem 0;
}
.loading.show { display: block; }
.loading-text {
  font-size: 0.8rem; letter-spacing: 0.1em; text-transform: uppercase;
  color: var(--g500); animation: pulse 1.5s ease-in-out infinite;
}
@keyframes pulse { 0%,100%{opacity:0.4} 50%{opacity:1} }

.error-box {
  display: none; border: 0.5px solid #e24b4a; padding: 1.2rem 1.5rem;
  font-size: 0.85rem; color: #a32d2d; margin-bottom: 1.5rem;
}
.error-box.show { display: block; }

/* TRY AGAIN */
.try-again {
  display: none; text-align: center; padding: 1.5rem 0;
}
.try-again.show { display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap; }
.chip {
  font-size: 0.8rem; padding: 0.5rem 1rem;
  border: 0.5px solid var(--g300); background: transparent;
  color: var(--g700); cursor: pointer; transition: all 0.2s;
  font-family: var(--sans);
}
.chip:hover { background: var(--g100); border-color: var(--black); color: var(--black); }

/* FOOTER */
footer {
  border-top: 0.5px solid var(--g300); padding: 1.5rem 3rem;
  display: flex; justify-content: space-between; align-items: center;
}
footer span { font-size: 0.75rem; color: var(--g500); }
footer .logo-sm { font-family: var(--serif); font-size: 0.95rem; color: var(--black); }
</style>
</head>
<body>

<nav>
  <span class="logo">Subsound</span>
  <span class="nav-tag">Music × Neuroscience</span>
</nav>

<div class="hero">
  <p class="hero-label">Where music becomes visible</p>
  <h1 class="hero-title">What does this song do <em>to your brain?</em></h1>
  <p class="hero-sub">Enter any song. Subsound reveals the neuroscience behind why it makes you feel exactly what it makes you feel.</p>
  <div class="search-wrap">
    <input type="text" id="songInput" placeholder="Song name + artist  e.g. Blinding Lights The Weeknd" />
    <button id="analyseBtn" onclick="analyseSong()">Analyse</button>
  </div>
  <div class="wave-row" id="waveRow"></div>
  <div class="try-again show" id="suggestions">
    <button class="chip" onclick="fillAndAnalyse('Blinding Lights — The Weeknd')">Blinding Lights</button>
    <button class="chip" onclick="fillAndAnalyse('Blue & Grey — BTS')">Blue & Grey — BTS</button>
    <button class="chip" onclick="fillAndAnalyse('Someone Like You — Adele')">Someone Like You</button>
    <button class="chip" onclick="fillAndAnalyse('DNA — BTS')">DNA — BTS</button>
  </div>
</div>

<div class="results" id="results" style="display:none;">
  <div class="error-box" id="errorBox"></div>

  <div class="loading" id="loading">
    <p class="loading-text">Analysing neural response…</p>
  </div>

  <div id="resultContent" style="display:none;">
    <div class="song-header">
      <div>
        <div class="song-title" id="rSongTitle"></div>
        <div class="song-artist" id="rSongArtist"></div>
      </div>
      <span class="song-badge">Brain Analysis</span>
    </div>

    <p class="section-label">Brain scanner — neural response map</p>
    <div class="brain-grid" id="brainGrid"></div>

    <p class="section-label">Emotion fingerprint</p>
    <div class="fingerprint-section">
      <div class="fp-canvas-wrap">
        <canvas id="fpCanvas" width="260" height="260"></canvas>
      </div>
      <div class="fp-legend">
        <h3 id="fpTitle">Your emotion fingerprint</h3>
        <p id="fpDesc"></p>
        <div class="fp-tags" id="fpTags"></div>
      </div>
    </div>

    <div class="narrative-box">
      <h3>Why you feel this way</h3>
      <p id="narrative"></p>
    </div>
  </div>
</div>

<footer>
  <span class="logo-sm">Subsound</span>
  <span>Free forever · Powered by neuroscience research</span>
</footer>

<script>
// Wave bars
const waveRow = document.getElementById('waveRow');
const wHeights = [6,10,16,22,30,38,46,50,46,38,32,40,50,40,32,26,18,26,32,40,50,40,32,24,16,10,8,12,18,26,34,26,18,10,6];
wHeights.forEach((h,i) => {
  const b = document.createElement('div');
  b.className = 'wbar';
  b.style.height = '4px';
  b.style.setProperty('--h', h+'px');
  waveRow.appendChild(b);
});

let waveAnim;
function animateWave(active) {
  clearInterval(waveAnim);
  const bars = document.querySelectorAll('.wbar');
  if (!active) {
    bars.forEach(b => { b.style.height = '4px'; b.classList.remove('active'); });
    return;
  }
  bars.forEach(b => b.classList.add('active'));
  waveAnim = setInterval(() => {
    bars.forEach(b => {
      const h = 4 + Math.random() * 42;
      b.style.height = Math.round(h) + 'px';
    });
  }, 180);
}

function fillAndAnalyse(text) {
  document.getElementById('songInput').value = text;
  analyseSong();
}

async function analyseSong() {
  const input = document.getElementById('songInput').value.trim();
  if (!input) return;

  document.getElementById('results').style.display = 'block';
  document.getElementById('loading').classList.add('show');
  document.getElementById('resultContent').style.display = 'none';
  document.getElementById('errorBox').classList.remove('show');
  document.getElementById('suggestions').classList.remove('show');
  document.getElementById('analyseBtn').disabled = true;
  animateWave(true);

  const prompt = `You are Subsound, a neuroscience music analysis tool. Analyse the song: "${input}"

Return ONLY a valid JSON object with this exact structure (no markdown, no backticks, no extra text):
{
  "song": "Song Title",
  "artist": "Artist Name",
  "metrics": [
    {"name": "Tempo", "value": "128 BPM", "score": 72, "explanation": "One sentence neuroscience explanation of what this tempo does to the brain."},
    {"name": "Emotional Valence", "value": "High", "score": 80, "explanation": "One sentence about emotional positivity and brain reward circuits."},
    {"name": "Energy Level", "value": "Intense", "score": 88, "explanation": "One sentence about arousal and the autonomic nervous system."},
    {"name": "Dopamine Trigger", "value": "Strong", "score": 85, "explanation": "One sentence about anticipation and reward prediction."},
    {"name": "Memory Activation", "value": "Moderate", "score": 60, "explanation": "One sentence about hippocampal engagement and autobiographical memory."},
    {"name": "Motor Cortex", "value": "High", "score": 78, "explanation": "One sentence about rhythmic entrainment and the urge to move."}
  ],
  "fingerprint": {
    "title": "2-4 word poetic description of the song's emotional character",
    "description": "2 sentences describing what makes this song's emotional fingerprint unique from a neuroscience perspective.",
    "tags": ["tag1", "tag2", "tag3", "tag4"],
    "color1": "#hex color that matches the emotional tone",
    "color2": "#hex second color",
    "shape": "circular OR angular OR flowing OR fragmented"
  },
  "narrative": "3-4 sentences explaining in plain language exactly why this song makes listeners feel what they feel, using real neuroscience concepts like dopamine, the limbic system, auditory cortex, frisson, motor entrainment. Make it personal and fascinating."
}

Be accurate to the actual song if you know it. Use real neuroscience. Make scores realistic (not all high).`;

  try {
    const res = await fetch('https://api.anthropic.com/v1/messages', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        model: 'claude-sonnet-4-20250514',
        max_tokens: 1000,
        messages: [{ role: 'user', content: prompt }]
      })
    });

    const data = await res.json();
    const text = data.content.map(i => i.text || '').join('');
    const clean = text.replace(/```json|```/g, '').trim();
    const parsed = JSON.parse(clean);
    renderResults(parsed);
  } catch(e) {
    document.getElementById('loading').classList.remove('show');
    const eb = document.getElementById('errorBox');
    eb.textContent = 'Something went wrong analysing that song. Try again with a different song name.';
    eb.classList.add('show');
    animateWave(false);
  }

  document.getElementById('analyseBtn').disabled = false;
}

function renderResults(d) {
  document.getElementById('loading').classList.remove('show');
  animateWave(false);

  document.getElementById('rSongTitle').textContent = d.song;
  document.getElementById('rSongArtist').textContent = d.artist;

  // Brain grid
  const grid = document.getElementById('brainGrid');
  grid.innerHTML = '';
  d.metrics.forEach((m, i) => {
    const card = document.createElement('div');
    card.className = 'brain-card';
    card.innerHTML = `
      <div class="bc-metric">${m.name}</div>
      <div class="bc-value">${m.value}</div>
      <div class="bc-bar-track"><div class="bc-bar-fill" id="bar${i}" style="width:0%"></div></div>
      <div class="bc-explain">${m.explanation}</div>`;
    grid.appendChild(card);
    setTimeout(() => {
      document.getElementById('bar'+i).style.width = m.score + '%';
    }, 100 + i * 80);
  });

  // Fingerprint canvas
  drawFingerprint(d.fingerprint, d.metrics);

  document.getElementById('fpTitle').textContent = d.fingerprint.title;
  document.getElementById('fpDesc').textContent = d.fingerprint.description;

  const tagsEl = document.getElementById('fpTags');
  tagsEl.innerHTML = '';
  d.fingerprint.tags.forEach(t => {
    const span = document.createElement('span');
    span.className = 'fp-tag';
    span.textContent = t;
    tagsEl.appendChild(span);
  });

  document.getElementById('narrative').textContent = d.narrative;

  document.getElementById('resultContent').style.display = 'block';
  document.getElementById('resultContent').scrollIntoView({ behavior: 'smooth', block: 'start' });
}

function drawFingerprint(fp, metrics) {
  const canvas = document.getElementById('fpCanvas');
  const ctx = canvas.getContext('2d');
  const W = canvas.width, H = canvas.height;
  ctx.clearRect(0, 0, W, H);

  const cx = W/2, cy = H/2;
  const scores = metrics.map(m => m.score / 100);
  const c1 = fp.color1 || '#0e0e0e';
  const c2 = fp.color2 || '#9a9890';
  const shape = fp.shape || 'circular';

  // Background rings
  for (let r = 110; r > 10; r -= 18) {
    ctx.beginPath();
    ctx.arc(cx, cy, r, 0, Math.PI * 2);
    ctx.strokeStyle = `rgba(200,198,192,${0.15 + (110-r)/200})`;
    ctx.lineWidth = 0.5;
    ctx.stroke();
  }

  // Unique shape based on metrics
  const points = scores.length;
  const angleStep = (Math.PI * 2) / points;

  if (shape === 'circular' || shape === 'flowing') {
    // Smooth blob
    ctx.beginPath();
    for (let i = 0; i <= points; i++) {
      const idx = i % points;
      const angle = idx * angleStep - Math.PI / 2;
      const r = 30 + scores[idx] * 75;
      const wobble = shape === 'flowing' ? Math.sin(angle * 3) * 8 : 0;
      const x = cx + Math.cos(angle) * (r + wobble);
      const y = cy + Math.sin(angle) * (r + wobble);
      if (i === 0) ctx.moveTo(x, y);
      else {
        const prevIdx = (i-1) % points;
        const prevAngle = prevIdx * angleStep - Math.PI/2;
        const pr = 30 + scores[prevIdx] * 75;
        const pw = shape === 'flowing' ? Math.sin(prevAngle * 3) * 8 : 0;
        const px = cx + Math.cos(prevAngle) * (pr + pw);
        const py = cy + Math.sin(prevAngle) * (pr + pw);
        const cpx = (px + x) / 2;
        const cpy = (py + y) / 2;
        ctx.quadraticCurveTo(px, py, cpx, cpy);
      }
    }
    ctx.closePath();
    const grad = ctx.createRadialGradient(cx, cy, 0, cx, cy, 100);
    grad.addColorStop(0, c1 + '33');
    grad.addColorStop(1, c2 + '22');
    ctx.fillStyle = grad;
    ctx.fill();
    ctx.strokeStyle = c1;
    ctx.lineWidth = 1.5;
    ctx.stroke();

  } else {
    // Angular / fragmented
    ctx.beginPath();
    for (let i = 0; i < points; i++) {
      const angle = i * angleStep - Math.PI / 2;
      const r = 30 + scores[i] * 75;
      const x = cx + Math.cos(angle) * r;
      const y = cy + Math.sin(angle) * r;
      if (i === 0) ctx.moveTo(x, y);
      else ctx.lineTo(x, y);
    }
    ctx.closePath();
    ctx.fillStyle = c1 + '22';
    ctx.fill();
    ctx.strokeStyle = c1;
    ctx.lineWidth = 1.5;
    ctx.stroke();

    // Inner shape
    ctx.beginPath();
    for (let i = 0; i < points; i++) {
      const angle = i * angleStep - Math.PI / 2;
      const r = 15 + scores[i] * 35;
      const x = cx + Math.cos(angle) * r;
      const y = cy + Math.sin(angle) * r;
      if (i === 0) ctx.moveTo(x, y);
      else ctx.lineTo(x, y);
    }
    ctx.closePath();
    ctx.strokeStyle = c2;
    ctx.lineWidth = 0.8;
    ctx.stroke();
  }

  // Center dot
  ctx.beginPath();
  ctx.arc(cx, cy, 3, 0, Math.PI * 2);
  ctx.fillStyle = c1;
  ctx.fill();

  // Metric spokes
  scores.forEach((s, i) => {
    const angle = i * angleStep - Math.PI/2;
    const r = 30 + s * 75;
    ctx.beginPath();
    ctx.moveTo(cx, cy);
    ctx.lineTo(cx + Math.cos(angle)*r, cy + Math.sin(angle)*r);
    ctx.strokeStyle = c1 + '30';
    ctx.lineWidth = 0.5;
    ctx.stroke();
  });
}

// Enter key support
document.getElementById('songInput').addEventListener('keydown', e => {
  if (e.key === 'Enter') analyseSong();
});
</script>
</body>
</html>
