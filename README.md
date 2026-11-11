# TechAcademy-Intro<!DOCTYPE html>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Welcome. Chill. This is just an Ice Breaker!</title>
<!-- Google Fonts: Barlow Condensed (Semibold 600/700) for Headings, Roboto for Body -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:ital,wght@0,600;0,700;1,600&family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
<style>
:root {
  /* Official Tagmarshal Primary Brand Palette */
  --tm-green: #89BF40;
  --tm-gray: #313131;
  /* Brand Accents */
  --tm-orange: #FF9933;
  --tm-yellow: #FFD700;
  --tm-red: #E93939;
  --tm-blue: #0090D0;
  --tm-magenta: #A04B9D;
  /* Official Brand Dark Gradient & Surface Colors */
  --tm-bg-start: #30383D;
  --tm-bg-end: #191D21;
  --tm-panel-bg: rgba(25, 29, 33, 0.90);
  --tm-panel-border: #3d474e;
  --tm-text-light: #F5F5F5;
  --tm-text-muted: #B0BEC5;
  /* Brand Fonts */
  --font-heading: 'Barlow Condensed', sans-serif;
  --font-body: 'Roboto', sans-serif;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  background: radial-gradient(circle at top center, var(--tm-bg-start), var(--tm-bg-end) 85%);
  color: var(--tm-text-light);
  font-family: var(--font-body);
  font-size: 16px;
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
}

.wrap {
  max-width: 880px;
  margin: auto;
  padding: 24px 20px;
}

/* Header & Official Brand Shield */
.brand {
  display: flex;
  align-items: center;
  gap: 14px;
  margin-bottom: 20px;
}

.logo-shield {
  width: 44px;
  height: 44px;
  flex-shrink: 0;
  filter: drop-shadow(0 3px 6px rgba(0,0,0,0.35));
}

.logo-text-group {
  display: flex;
  flex-direction: column;
}

.logo-wordmark {
  font-family: var(--font-heading);
  font-size: 1.9rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  line-height: 1;
  color: #FFFFFF;
  text-transform: uppercase;
}

.logo-byline {
  font-family: var(--font-body);
  font-size: 0.75rem;
  letter-spacing: 0.04em;
  color: var(--tm-text-muted);
  text-transform: lowercase;
  margin-top: 2px;
}

.tag {
  background: rgba(137, 191, 64, 0.15);
  border: 1px solid var(--tm-green);
  color: var(--tm-green);
  font-family: var(--font-heading);
  font-size: 0.85rem;
  font-weight: 600;
  letter-spacing: 0.08em;
  padding: 4px 10px;
  border-radius: 6px;
  text-transform: uppercase;
  margin-left: auto;
}

/* Glassmorphism Card Style */
.card {
  background: var(--tm-panel-bg);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  border: 1px solid var(--tm-panel-border);
  border-radius: 14px;
  padding: clamp(20px, 4vw, 36px);
  box-shadow: 0 16px 40px rgba(0, 0, 0, 0.45);
  margin-top: 12px;
}

/* Headings in Barlow Condensed, Semi-bold 600/700, All-Caps */
h1, h2, h3 {
  font-family: var(--font-heading);
  text-transform: uppercase;
  font-weight: 600;
  letter-spacing: 0.03em;
  margin: 0.3em 0 0.5em;
}

h1 {
  font-size: clamp(2rem, 5.5vw, 3.4rem);
  line-height: 1.05;
}

h2 {
  font-size: clamp(1.35rem, 3.2vw, 1.9rem);
  color: #FFFFFF;
}

p {
  color: var(--tm-text-muted);
  margin: 0 0 1.2em;
}

label {
  display: block;
  font-family: var(--font-heading);
  font-size: 0.95rem;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  color: var(--tm-text-light);
  margin-bottom: 5px;
}

input {
  width: 100%;
  padding: 12px 14px;
  border-radius: 8px;
  border: 1px solid var(--tm-panel-border);
  background: #14171a;
  color: #FFFFFF;
  font-family: var(--font-body);
  font-size: 1rem;
  margin: 4px 0 16px;
  outline: none;
  transition: border-color 0.2s, box-shadow 0.2s;
}

input:focus {
  border-color: var(--tm-green);
  box-shadow: 0 0 0 3px rgba(137, 191, 64, 0.25);
}

/* Buttons */
button {
  font-family: var(--font-heading);
  font-size: 1.1rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  cursor: pointer;
  border: none;
  border-radius: 8px;
  padding: 12px 20px;
  background: var(--tm-green);
  color: #191D21;
  transition: all 0.2s ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

button:hover:not(:disabled) {
  background: #9bd24d;
  box-shadow: 0 4px 14px rgba(137, 191, 64, 0.35);
}

button.secondary {
  background: #252a2e;
  color: var(--tm-text-light);
  border: 1px solid var(--tm-panel-border);
}

button.secondary:hover:not(:disabled) {
  background: #31383d;
  border-color: #526068;
}

button:disabled {
  opacity: 0.45;
  cursor: not-allowed;
}

.row {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

.row > * {
  flex: 1;
}

.hidden {
  display: none !important;
}

/* Indicators and Progress */
.pill {
  display: inline-block;
  background: rgba(137, 191, 64, 0.12);
  border: 1px solid rgba(137, 191, 64, 0.5);
  padding: 5px 12px;
  border-radius: 4px;
  color: var(--tm-green);
  font-family: var(--font-heading);
  font-size: 0.85rem;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

.progress {
  height: 7px;
  background: #23292e;
  border-radius: 4px;
  overflow: hidden;
  margin: 18px 0;
  border: 1px solid #363e44;
}

.progress span {
  display: block;
  height: 100%;
  background: var(--tm-green);
  width: 0;
  transition: width 0.25s ease;
}

/* Quiz Option Buttons */
.options {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
  gap: 12px;
  margin: 20px 0;
}

.opt {
  background: #252c30;
  color: #FFFFFF;
  text-align: left;
  font-family: var(--font-body);
  font-size: 0.95rem;
  font-weight: 400;
  letter-spacing: normal;
  text-transform: none;
  border: 2px solid transparent;
  border-radius: 8px;
  padding: 13px 16px;
  min-height: 68px;
  line-height: 1.35;
  justify-content: flex-start;
  transition: all 0.2s;
}

.opt:hover:not(:disabled) {
  background: #2e363c;
  border-color: #4a5760;
}

.opt.selected {
  border-color: var(--tm-green);
  background: rgba(137, 191, 64, 0.15);
}

.opt.correct {
  background: rgba(137, 191, 64, 0.22) !important;
  border-color: var(--tm-green) !important;
  color: #FFFFFF !important;
}

.opt.wrong {
  background: rgba(233, 57, 57, 0.22) !important;
  border-color: var(--tm-red) !important;
  color: #FFFFFF !important;
}

/* Feedback Box */
.feedback {
  padding: 14px 18px;
  border-radius: 8px;
  background: #252c31;
  border-left: 4px solid var(--tm-green);
  margin: 12px 0;
  font-size: 0.95rem;
  line-height: 1.45;
  color: var(--tm-text-light);
}

.scorebig {
  font-family: var(--font-heading);
  font-size: 3.5rem;
  color: var(--tm-green);
  font-weight: 700;
  line-height: 1;
  margin: 8px 0 14px;
}

/* Leaderboard */
.leader {
  width: 100%;
  border-collapse: collapse;
  margin-top: 12px;
}

.leader th {
  font-family: var(--font-heading);
  text-transform: uppercase;
  color: var(--tm-green);
  letter-spacing: 0.06em;
  font-size: 0.92rem;
  padding: 10px 8px;
  border-bottom: 2px solid #3d474e;
  text-align: left;
}

.leader td {
  padding: 10px 8px;
  border-bottom: 1px solid #2e363c;
  color: var(--tm-text-light);
  font-size: 0.95rem;
}

.leader tbody tr:hover {
  background: rgba(255, 255, 255, 0.03);
}

.small {
  font-size: 0.88rem;
}

.footer {
  text-align: center;
  color: #71818c;
  font-family: var(--font-heading);
  letter-spacing: 0.08em;
  font-size: 0.85rem;
  text-transform: uppercase;
  padding: 24px;
}
</style>
</head>
<body><main class="wrap">

<header class="brand">
  <svg class="logo-shield" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
    <circle cx="100" cy="100" r="96" fill="#89BF40"/>
    <circle cx="100" cy="100" r="70" fill="#EAEAEA" filter="drop-shadow(0px 2px 4px rgba(0,0,0,0.25))"/>
    <circle cx="100" cy="100" r="46" fill="#89BF40"/>
  </svg>
  <div class="logo-text-group">
    <div class="logo-wordmark">TAGMARSHAL</div>
    <div class="logo-byline">golf course optimization</div>
  </div>
  <span class="tag">TECH ACADEMY</span>
</header>

<section id="welcome" class="card">
<span class="pill">ONLINE ICEBREAKER • 10–15 MIN</span>
<h1>Welcome. Chill.<br><span style="color:var(--tm-green)">This is just an Ice Breaker!</span></h1>
<p>Welcome to the Tagmarshal Tech Academy! Warm up, test your knowledge, and celebrate your learning journey.</p>
<label for="player">Your name</label><input id="player" maxlength="30" placeholder="Enter your name">
<label for="team">Team name (optional)</label><input id="team" maxlength="30" placeholder="e.g. Fairway Fixers">
<div class="row"><button onclick="start()">Let's play →</button><button class="secondary" onclick="showBoard()">View leaderboard</button></div>
<p class="small">Play solo or share your screen in a group. Your score is saved on this device.</p>
</section>

<section id="game" class="card hidden">
<div class="row"><span class="pill" id="qcount">QUESTION 1 / 6</span><span class="pill" id="timer">POINTS: 0</span></div><div class="progress"><span id="bar"></span></div>
<h2 id="question"></h2><div id="options" class="options"></div><div id="feedback" class="feedback hidden"></div>
<div class="row"><button id="submit" onclick="submitAnswer()" disabled>Lock in answer</button><button id="next" class="secondary hidden" onclick="nextQuestion()">Next challenge →</button></div>
</section>

<section id="challenge" class="card hidden"><span class="pill">BONUS TEAM CHALLENGE</span><h2>Two-word tech check-in</h2><p>In the chat, share <b>two words</b> describing how you feel about starting your LMS journey (for example: “curious + ready”).</p><p>Then complete this pledge:</p><h2 style="color:var(--tm-green)">“At Tech Academy, I will…”</h2><p>Say it out loud or type it in the meeting chat. This challenge is for team spirit—no extra points needed!</p><button onclick="finish()">Reveal my result →</button></section>

<section id="result" class="card hidden"><span class="pill">TECH ACADEMY FINISHER</span><h1 id="congrats">Well played!</h1><div class="scorebig" id="finalscore">0</div><p id="resultcopy"></p><div class="row"><button onclick="saveScore()">Save to this device's leaderboard</button><button class="secondary" onclick="showBoard()">Leaderboard</button></div><div class="feedback">🏆 <b>Tech Academy Champion moment:</b> Celebrate your effort—and cheer on your teammates!</div><button onclick="restart()">Play again</button></section>

<section id="board" class="card hidden"><h2>🏆 Local leaderboard</h2><p>Scores saved in this browser only (not shared live with other players).</p><table class="leader"><thead><tr><th>#</th><th>Technician</th><th>Team</th><th>Score</th></tr></thead><tbody id="scores"></tbody></table><div class="row" style="margin-top:16px"><button onclick="backHome()">Back</button><button class="secondary" onclick="clearBoard()">Clear leaderboard</button></div></section>

<div class="footer">TAGMARSHAL TECH ACADEMY • LEARN. CONNECT. GROW.</div>
</main>

<script>
const qs=[
{q:"What does LMS stand for?",a:["Learning Management System","Line Maintenance Support","Local Management Software","Learning Made Simple"],c:0,why:"An LMS is a Learning Management System: a platform for delivering and tracking learning."},
{q:"When a theory module is unclear, what is the best next step?",a:["Guess and move on","Ask a facilitator or teammate and revisit it","Skip every related module","Wait until the final assessment"],c:1,why:"Ask for support, revisit the material, and clarify before moving forward."},
{q:"Which quality helps technicians solve unfamiliar problems?",a:["Avoiding questions","Working without communicating","Curiosity and structured troubleshooting","Rushing to the first solution"],c:2,why:"Curiosity and a systematic approach help you investigate and resolve issues."},
{q:"A teammate is struggling with a learning activity. What can you do?",a:["Offer encouragement and explain what helped you","Complete it for them","Ignore the situation","Tell them learning is only individual"],c:0,why:"Peer support builds confidence while allowing each person to learn."},
{q:"Why is theory learning useful before practical work?",a:["It replaces all hands-on practice","It builds understanding and prepares you for application","It guarantees every fault has one solution","It is only for passing a quiz"],c:1,why:"Theory gives concepts and context that technicians can apply during practical training."},
{q:"What is a strong Tech Academy mindset?",a:["I must know everything already","Mistakes mean I should stop","Only scores matter","I can learn, ask questions, and improve"],c:3,why:"A growth mindset values effort, questions, feedback, and improvement."}
];
let idx=0,score=0,chosen=null,player="",team="";
function hideAll(){["welcome","game","challenge","result","board"].forEach(x=>document.getElementById(x).classList.add("hidden"))}
function start(){player=document.getElementById("player").value.trim()||"Tech";team=document.getElementById("team").value.trim()||"—";idx=0;score=0;hideAll();document.getElementById("game").classList.remove("hidden");render()}
function render(){chosen=null;document.getElementById("qcount").textContent=`QUESTION ${idx+1} / ${qs.length}`;document.getElementById("timer").textContent=`POINTS: ${score}`;document.getElementById("bar").style.width=`${idx/qs.length*100}%`;document.getElementById("question").textContent=qs[idx].q;let box=document.getElementById("options");box.innerHTML="";qs[idx].a.forEach((a,i)=>{let b=document.createElement("button");b.className="opt";b.textContent=["A","B","C","D"][i]+". "+a;b.onclick=()=>{if(document.getElementById("feedback").classList.contains("hidden")){chosen=i;[...box.children].forEach(x=>x.classList.remove("selected"));b.classList.add("selected");document.getElementById("submit").disabled=false}};box.appendChild(b)});document.getElementById("feedback").classList.add("hidden");document.getElementById("submit").classList.remove("hidden");document.getElementById("submit").disabled=true;document.getElementById("next").classList.add("hidden")}
function submitAnswer(){if(chosen===null)return;let q=qs[idx],good=chosen===q.c;if(good)score+=100;let opts=[...document.getElementById("options").children];opts[q.c].classList.add("correct");if(!good)opts[chosen].classList.add("wrong");let f=document.getElementById("feedback");f.textContent=(good?"✨ Nice one! +100 points. ":"Not quite—keep learning. ")+q.why;f.classList.remove("hidden");document.getElementById("submit").classList.add("hidden");document.getElementById("next").classList.remove("hidden");document.getElementById("timer").textContent=`POINTS: ${score}`}
function nextQuestion(){idx++;if(idx<qs.length)render();else{hideAll();document.getElementById("challenge").classList.remove("hidden")}}
function finish(){hideAll();document.getElementById("result").classList.remove("hidden");document.getElementById("congrats").textContent=score>=500?"Tech Academy Star!":score>=300?"Great work, "+player+"!":"Well played, "+player+"!";document.getElementById("finalscore").textContent=score+" POINTS";document.getElementById("resultcopy").textContent=`You completed all ${qs.length} questions. Keep learning, keep growing, and support your team!`}
function saveScore(){let data=JSON.parse(localStorage.getItem("tagmarshalScores")||"[]");data.push({name:player,team,score,date:new Date().toLocaleDateString()});data.sort((a,b)=>b.score-a.score);localStorage.setItem("tagmarshalScores",JSON.stringify(data.slice(0,50)));showBoard()}
function showBoard(){hideAll();document.getElementById("board").classList.remove("hidden");let data=JSON.parse(localStorage.getItem("tagmarshalScores")||"[]");document.getElementById("scores").innerHTML=data.length?data.map((x,i)=>`<tr><td>${i+1}</td><td>${esc(x.name)}</td><td>${esc(x.team)}</td><td>${x.score}</td></tr>`).join(""):'<tr><td colspan="4">No saved scores yet—play a round!</td></tr>'}
function esc(s){return String(s).replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]))}
function backHome(){hideAll();document.getElementById("welcome").classList.remove("hidden")}
function restart(){backHome();document.getElementById("player").value=player;document.getElementById("team").value=team}
function clearBoard(){if(confirm("Clear scores saved on this browser?")){localStorage.removeItem("tagmarshalScores");showBoard()}}
</script>
</body>
</html>
