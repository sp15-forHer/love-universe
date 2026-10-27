# love-universe

import streamlit as st
import streamlit.components.v1 as components

st.set_page_config(
    page_title="A Thousand Languages, One Heart",
    page_icon="💗",
    layout="wide"
)

pagina = r"""
<!DOCTYPE html>
<html lang="it">
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
* { box-sizing: border-box; }

html, body {
    margin: 0;
    background: #090410;
    color: #fff0fa;
    font-family: Georgia, serif;
    text-align: center;
}

body {
    overflow-x: hidden;
    background:
      radial-gradient(ellipse at 50% 20%, #431044 0%, transparent 45%),
      radial-gradient(ellipse at 10% 80%, #241044 0%, transparent 40%),
      #090410;
}

#stars {
    position: fixed;
    inset: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 0;
}

main {
    position: relative;
    z-index: 1;
    width: min(100%, 680px);
    margin: auto;
    padding: 48px 18px 70px;
}

.eyebrow {
    color: #e9a6dc;
    letter-spacing: 4px;
    font-size: 10px;
    text-transform: uppercase;
}

h1 {
    font-size: clamp(31px, 8vw, 53px);
    font-weight: normal;
    line-height: 1.15;
    margin: 20px 0 10px;
    text-shadow: 0 0 25px #ff43cb;
}

.subtitle {
    color: #d8b6d9;
    font-style: italic;
    font-size: 15px;
}

.heart-area {
    height: 235px;
    display: grid;
    place-items: center;
    position: relative;
}

.heart {
    font-size: 115px;
    line-height: 1;
    color: #ff3ca6;
    filter: drop-shadow(0 0 14px #ff168c)
            drop-shadow(0 0 40px #b400ff);
    animation: beat 1.15s infinite;
}

.orbit {
    position: absolute;
    width: 200px;
    height: 75px;
    border: 1px solid #ff8cdd88;
    border-radius: 50%;
    transform: rotate(-22deg);
    box-shadow: 0 0 15px #ff45cc33;
    animation: orbit 8s linear infinite;
}

@keyframes beat {
    0%, 100% { transform: scale(1); }
    14% { transform: scale(1.13); }
    28% { transform: scale(1); }
    42% { transform: scale(1.18); }
    60% { transform: scale(1); }
}

@keyframes orbit {
    to { transform: rotate(338deg); }
}

h2 {
    font-weight: normal;
    font-size: 23px;
    margin-top: 25px;
}

.words {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 12px;
    margin: 25px 0;
}

.word {
    padding: 16px 5px;
    border: 1px solid #c85baf55;
    border-radius: 14px;
    background: #ffffff06;
    box-shadow: 0 0 20px #ff32bd08;
    animation: glow 3s ease-in-out infinite alternate;
}

.word strong {
    display: block;
    color: #ffb6e9;
    font-size: 19px;
    font-weight: normal;
}

.word small {
    display: block;
    color: #bda3c4;
    margin-top: 7px;
}

@keyframes glow {
    from { border-color: #c85baf33; }
    to { border-color: #ff70d988; }
}

button {
    font-family: Georgia, serif;
    color: white;
    background: linear-gradient(120deg, #8c176d, #4d176d);
    border: 1px solid #ff8bdd;
    padding: 14px 22px;
    border-radius: 30px;
    font-size: 15px;
    margin: 8px;
    cursor: pointer;
    box-shadow: 0 0 20px #e72caf30;
}

button:active { transform: scale(.97); }

#extra {
    min-height: 44px;
    color: #ffbce8;
    font-size: 23px;
    font-style: italic;
    margin: 15px 0;
}

.letter {
    margin-top: 48px;
    padding: 28px 20px;
    border: 1px solid #e17acb99;
    border-radius: 18px;
    background: linear-gradient(145deg, #1b0d25ee, #100817ee);
    box-shadow: 0 0 45px #d51d9c20;
    line-height: 1.9;
}

.letter h2 {
    color: #ffc2ed;
    font-style: italic;
}

#message {
    white-space: pre-line;
    color: #ead8e9;
    font-size: 16px;
}

.signature {
    color: #ff9dde;
    font-size: 21px;
    font-style: italic;
    margin-top: 22px;
}

#ending {
    display: none;
    padding: 45px 5px 20px;
    animation: appear 2s ease both;
}

#ending h2 {
    font-size: 38px;
    color: #ffb3e8;
    text-shadow: 0 0 25px #ff32c8;
}

#fireworks {
    position: fixed;
    inset: 0;
    pointer-events: none;
    width: 100%;
    height: 100%;
    z-index: 5;
}

@keyframes appear {
    from { opacity: 0; transform: translateY(15px); }
    to { opacity: 1; transform: translateY(0); }
}

footer {
    color: #a78aaf;
    font-size: 12px;
    margin-top: 40px;
    letter-spacing: 1px;
}

@media (max-width: 360px) {
    main { padding-left: 12px; padding-right: 12px; }
    .word strong { font-size: 16px; }
}
</style>
</head>

<body>
<canvas id="stars"></canvas>
<canvas id="fireworks"></canvas>

<main>
    <div class="eyebrow">A little universe, made for you</div>

    <h1>A Thousand Languages,<br>One Heart</h1>

    <div class="subtitle">
        Different words. The same love. Always you.
    </div>

    <div class="heart-area">
        <div class="orbit"></div>
        <div class="heart">♥</div>
    </div>

    <h2>In every language, I choose you.</h2>

    <div class="words">
        <div class="word"><strong>Ti amo</strong><small>Italiano</small></div>
        <div class="word"><strong>I love you</strong><small>Inglese</small></div>
        <div class="word"><strong>ฉันรักเธอ</strong><small>Thailandese</small></div>
        <div class="word"><strong>愛してる</strong><small>Giapponese</small></div>
        <div class="word"><strong>사랑해</strong><small>Coreano</small></div>
        <div class="word"><strong>Je t'aime</strong><small>Francese</small></div>
        <div class="word"><strong>Te quiero</strong><small>Spagnolo</small></div>
        <div class="word"><strong>Ich liebe dich</strong><small>Tedesco</small></div>
        <div class="word"><strong>我愛你</strong><small>Cinese tradizionale</small></div>
        <div class="word"><strong>Я тебя люблю</strong><small>Russo</small></div>
        <div class="word"><strong>Seni seviyorum</strong><small>Turco</small></div>
        <div class="word"><strong>Eu te amo</strong><small>Portoghese</small></div>
    </div>

    <button onclick="anotherLove()">Scopri un altro “ti amo” ✧</button>
    <div id="extra"></div>

    <section class="letter">
        <div class="eyebrow">A letter from my heart</div>
        <h2>Alla mia persona preferita,</h2>
        <div id="message"></div>
        <div class="signature">Tua, oggi e ogni domani. ♡</div>
    </section>

    <button onclick="revealLetter()">Leggi la mia lettera ♡</button>
    <button onclick="finale()">Apri il nostro universo ✨</button>

    <section id="ending">
        <div class="heart">♥</div>
        <h2>ฉันรักเธอ</h2>
        <h2>I LOVE YOU</h2>
        <p style="font-style:italic;line-height:1.9">
            In every language.<br>
            In every universe.<br>
            In every version of tomorrow.<br><br>
            <strong>You. Always you. ♡</strong>
        </p>
    </section>

    <footer>MADE WITH ALL MY HEART · FOREVER YOURS</footer>
</main>

<script>
const loveWords = [
    ["Mi amas", "Latino"],
    ["Te iubesc", "Rumeno"],
    ["Kocham cię", "Polacco"],
    ["Mahal kita", "Filippino"],
    ["Jeg elsker dig", "Danese"],
    ["Ek het jou lief", "Afrikaans"],
    ["Naan unnai kaadhalikkiren", "Tamil"],
    ["أحبك", "Arabo"],
    ["Я тебя люблю", "Russo"],
    ["Volim te", "Serbo-croato"]
];

let wordIndex = 0;

function anotherLove() {
    const item = loveWords[wordIndex % loveWords.length];
    document.getElementById("extra").textContent =
        item[0] + " ♡ — " + item[1];
    wordIndex++;
}

const letterText =
`Non esistono parole abbastanza belle
per descrivere ciò che provo per te.

Sei la mia pace, la mia felicità,
il mio posto sicuro in questo mondo.

Non ho bisogno di un amore perfetto.
Voglio un amore vero, fatto di piccoli gesti,
di pazienza, di risate e di momenti
in cui scegliamo ancora di esserci.

Ti amo in ogni lingua, in ogni forma,
in ogni momento.
Non perché tu debba darmi qualcosa,
ma perché il mio cuore ti sceglie,
liberamente, con tutto se stesso.

Se il mondo avesse mille lingue,
le userei tutte per dirti la stessa cosa:
I love you. ฉันรักเธอ. Ti amo.

E se un giorno finissero le parole,
spero che tu possa guardarmi negli occhi
e sentire tutto quello che non so spiegare.

Tu, oggi. Tu, domani.
Tu, in ogni piccolo universo che sogno.

Per sempre, con tutto il mio cuore. ♡`;

let letterShown = false;

function revealLetter() {
    if (letterShown) return;
    letterShown = true;
    const el = document.getElementById("message");
    let i = 0;
    function type() {
        if (i < letterText.length) {
            el.textContent += letterText.charAt(i);
            i++;
            setTimeout(type, 24);
        }
    }
    type();
    document.querySelector(".letter").scrollIntoView({
        behavior: "smooth", block: "center"
    });
}

const stars = document.getElementById("stars");
const ctx = stars.getContext("2d");
let particles = [];

function resize() {
    stars.width = innerWidth * devicePixelRatio;
    stars.height = innerHeight * devicePixelRatio;
    stars.style.width = innerWidth + "px";
    stars.style.height = innerHeight + "px";
    ctx.setTransform(devicePixelRatio,0,0,devicePixelRatio,0,0);
    particles = [];
    for (let i=0; i<100; i++) {
        particles.push({
            x: Math.random()*innerWidth,
            y: Math.random()*innerHeight,
            r: Math.random()*1.7+.3,
            a: Math.random(),
            speed: Math.random()*.012+.003
        });
    }
}

function drawStars() {
    ctx.clearRect(0,0,innerWidth,innerHeight);
    particles.forEach(p => {
        p.a += p.speed;
        let alpha = .25 + (Math.sin(p.a)+1)*.35;
        ctx.beginPath();
        ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
        ctx.fillStyle = `rgba(255,190,240,${alpha})`;
        ctx.shadowBlur = 9;
        ctx.shadowColor = "#ff4fcb";
        ctx.fill();
    });
    requestAnimationFrame(drawStars);
}

window.addEventListener("resize", resize);
resize();
drawStars();

const fw = document.getElementById("fireworks");
const fx = fw.getContext("2d");
let sparks = [];
let fireworksOn = false;

function resizeFireworks() {
    fw.width = innerWidth * devicePixelRatio;
    fw.height = innerHeight * devicePixelRatio;
    fw.style.width = innerWidth + "px";
    fw.style.height = innerHeight + "px";
    fx.setTransform(devicePixelRatio,0,0,devicePixelRatio,0,0);
}
window.addEventListener("resize", resizeFireworks);
resizeFireworks();

function burst(x,y) {
    for(let i=0;i<65;i++) {
        let angle=Math.random()*Math.PI*2;
        let speed=Math.random()*4+1;
        sparks.push({
            x,y,
            vx:Math.cos(angle)*speed,
            vy:Math.sin(angle)*speed,
            life:1,
            hue:300+Math.random()*55
        });
    }
}

function drawFireworks() {
    fx.clearRect(0,0,innerWidth,innerHeight);
    sparks.forEach(p => {
        p.x += p.vx;
        p.y += p.vy;
        p.vy += .025;
        p.life -= .012;
        fx.beginPath();
        fx.arc(p.x,p.y,2,0,Math.PI*2);
        fx.fillStyle=`hsla(${p.hue},100%,75%,${Math.max(0,p.life)})`;
        fx.fill();
    });
    sparks = sparks.filter(p=>p.life>0);
    if(fireworksOn && Math.random()<.08) {
        burst(Math.random()*innerWidth,Math.random()*innerHeight*.65);
    }
    requestAnimationFrame(drawFireworks);
}
drawFireworks();

function finale() {
    document.getElementById("ending").style.display="block";
    fireworksOn = true;
    for(let i=0;i<5;i++) {
        setTimeout(()=>burst(
            innerWidth*(.15+Math.random()*.7),
            innerHeight*(.2+Math.random()*.45)
        ),i*350);
    }
    document.getElementById("ending").scrollIntoView({
        behavior:"smooth", block:"center"
    });
    revealLetter();
}
</script>
</body>
</html>
"""

components.html(pagina, height=3000, scrolling=True)
