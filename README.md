# TechAcademy-Intro<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8"><meta name="viewport" content="width=device-width,initial-scale=1">
<title>Tagmarshal Tech Academy — Icebreaker</title>
<style>
:root{--lime:#7ee33b;--green:#20a83a;--ink:#071713;--panel:#102820;--line:#28523c;--white:#f5fff7;--muted:#b7cdbd}
*{box-sizing:border-box}body{margin:0;background:radial-gradient(circle at top,#17442b,#06120f 65%);color:var(--white);font:16px/1.45 system-ui,Segoe UI,Arial}
.wrap{max-width:900px;margin:auto;padding:22px}.brand{display:flex;align-items:center;gap:12px;font-weight:800;letter-spacing:.04em}.mark{font-size:30px;color:var(--lime)}.tag{color:var(--lime);font-size:.8rem;letter-spacing:.15em}
.card{background:linear-gradient(145deg,#143526,#0b1d16);border:1px solid var(--line);border-radius:20px;padding:clamp(20px,4vw,36px);box-shadow:0 18px 50px #0005;margin-top:18px}
h1{font-size:clamp(2rem,6vw,4rem);line-height:1.02;margin:.4em 0}h2{margin:.2em 0 .7em}p{color:var(--muted)}button,input{font:inherit}button{cursor:pointer;border:0;border-radius:12px;padding:13px 18px;font-weight:750;background:var(--lime);color:#09200e}button.secondary{background:#183b29;color:var(--white);border:1px solid #39704b}button:disabled{opacity:.45;cursor:not-allowed}.row{display:flex;gap:10px;flex-wrap:wrap}.row>*{flex:1}.hidden{display:none!important}.pill{display:inline-block;border:1px solid #356447;padding:5px 10px;border-radius:99px;color:var(--lime);font-size:.8rem}.progress{height:8px;background:#254333;border-radius:99px;overflow:hidden;margin:18px 0}.progress span{display:block;height:100%;background:var(--lime);width:0;transition:.25s}.options{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:12px;margin:20px 0}.opt{background:#f5fff7;color:#102419;text-align:left;border:3px solid transparent;min-height:70px}.opt.selected{border-color:var(--lime);background:#dfffd0}.opt.correct{background:#c9ffc0}.opt.wrong{background:#ffd8d8;border-color:#d44}.feedback{padding:12px;border-radius:10px;background:#183b29;margin:10px 0}.scorebig{font-size:3rem;color:var(--lime);font-weight:900}.leader{width:100%;border-collapse:collapse}.leader td,.leader th{text-align:left;padding:10px;border-bottom:1px solid #2b503a}.leader th{color:var(--lime)}input{width:100%;padding:12px;border-radius:10px;border:1px solid #39704b;background:#06140e;color:white;margin:6px 0 14px}.small{font-size:.9rem}.footer{text-align:center;color:#7f9c89;padding:22px}
</style>
</head>
<body><main class="wrap">
<header class="brand"><span class="mark">◆</span><span>TAGMARSHAL</span><span class="tag">TECH ACADEMY</span></header>
<section id="welcome" class="card">
<span class="pill">ONLINE ICEBREAKER • 10–15 MIN</span>
<h1>Learn.<br><span style="color:var(--lime)">Connect. Grow.</span></h1>
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
<section id="challenge" class="card hidden"><span class="pill">BONUS TEAM CHALLENGE</span><h2>Two-word tech check-in</h2><p>In the chat, share <b>two words</b> describing how you feel about starting your LMS journey (for example: “curious + ready”).</p><p>Then complete this pledge:</p><h2 style="color:var(--lime)">“At Tech Academy, I will…”</h2><p>Say it out loud or type it in the meeting chat. This challenge is for team spirit—no extra points needed!</p><button onclick="finish()">Reveal my result →</button></section>
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
</script></body></html>
