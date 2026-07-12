<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Lebensluft – Finde deine Atemübung</title>
<style>
:root{
  --forest-900:#173d33;
  --forest-800:#1d4a3d;
  --forest-700:#28584a;
  --forest-600:#3b725f;
  --sage-100:#eef4ef;
  --sage-200:#dde9e1;
  --sage-300:#c9d9d0;
  --cream:#f8f6f1;
  --white:#ffffff;
  --text:#173d33;
  --muted:#5f756b;
  --line:#cfdbd4;
  --soft:#f5f8f6;
  --shadow:0 10px 28px rgba(23,61,51,.10);
  --radius:16px;
  --max:1140px;
}

*{box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{
  margin:0;
  font-family:"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
  background:linear-gradient(180deg,var(--cream) 0%, #f3f6f3 100%);
  color:var(--text);
  line-height:1.55;
}
.wrap{
  max-width:var(--max);
  margin:0 auto;
  padding:20px 20px 40px;
}
.hero{
  padding:8px 0 14px;
  border-bottom:3px solid var(--forest-700);
}
.brand-row{
  display:flex;
  align-items:center;
  gap:16px;
  flex-wrap:wrap;
}
.logo-slot{
  width:78px;
  height:78px;
  border-radius:18px;
  background:var(--white);
  border:1px solid var(--line);
  display:flex;
  align-items:center;
  justify-content:center;
  overflow:hidden;
  box-shadow:var(--shadow);
  flex:0 0 auto;
}
#brandLogo{
  display:none;
  width:100%;
  height:100%;
  object-fit:contain;
  padding:10px;
  background:var(--white);
}
.logo-placeholder{
  width:100%;
  height:100%;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:.82rem;
  font-weight:700;
  letter-spacing:.08em;
  color:var(--forest-700);
  background:linear-gradient(180deg,var(--sage-100),#f8fbf9);
}
.eyebrow{
  color:var(--forest-700);
  font-size:.88rem;
  font-weight:700;
  letter-spacing:.08em;
  text-transform:uppercase;
  margin-bottom:8px;
}
h1,h2,h3,button,.question-title,.result-kicker,.pattern{
  font-family:inherit;
}
h1{
  font-size:clamp(2rem,5vw,3.1rem);
  line-height:1.03;
  margin:0 0 12px;
  font-weight:750;
  letter-spacing:-.03em;
  color:var(--forest-900);
}
.intro{
  font-size:1.04rem;
  max-width:760px;
  color:var(--muted);
  margin:12px 0 8px;
}
.disclaimer{
  font-size:.84rem;
  color:var(--muted);
  margin:6px 0 0;
}
.card{
  background:rgba(255,255,255,.86);
  border:1px solid var(--line);
  border-radius:var(--radius);
  box-shadow:var(--shadow);
  padding:22px;
  margin-top:18px;
}
h2{
  font-size:1.35rem;
  margin:0 0 14px;
  color:var(--forest-900);
}
.question{margin-bottom:14px;}
.question-title{
  font-size:1rem;
  font-weight:700;
  margin-bottom:8px;
  color:var(--forest-900);
}
.option-grid{
  display:grid;
  grid-template-columns:repeat(2,minmax(0,1fr));
  gap:10px;
}
.option-grid.three{grid-template-columns:repeat(3,minmax(0,1fr));}
.option-grid.goal-grid{grid-template-columns:repeat(4,minmax(0,1fr));}
.option{position:relative;}
.option input{
  position:absolute;
  opacity:0;
  pointer-events:none;
}
.option label{
  display:block;
  border:1px solid var(--line);
  background:var(--white);
  color:var(--forest-900);
  padding:12px;
  border-radius:12px;
  cursor:pointer;
  transition:all .2s ease;
  min-height:48px;
  font-weight:500;
}
.option label:hover{
  border-color:var(--forest-700);
  background:var(--sage-100);
}
.option input:checked+label{
  background:var(--sage-100);
  border-color:var(--forest-700);
  color:var(--forest-900);
  box-shadow:inset 0 0 0 2px var(--forest-700);
}
details{
  border:1px solid var(--line);
  border-radius:12px;
  background:#fbfcfb;
  overflow:hidden;
  margin-top:4px;
}
summary{
  list-style:none;
  cursor:pointer;
  padding:14px 16px;
  font-weight:700;
  color:var(--forest-900);
  background:var(--sage-100);
}
summary::-webkit-details-marker{display:none;}
.details-inner{
  padding:12px 16px 16px;
  border-top:1px solid var(--line);
}
.help,.inline-note,.footer-note,.result-reason,.science-copy,.office-note,.cta-copy,.legal{
  color:var(--muted);
}
.help{margin:0 0 12px;}
.inline-note{
  font-size:.88rem;
  margin-top:8px;
}
.actions{
  display:flex;
  gap:12px;
  flex-wrap:wrap;
  margin-top:14px;
}
button, .link-btn{
  appearance:none;
  border:none;
  border-radius:999px;
  padding:13px 22px;
  font-size:1rem;
  font-weight:700;
  cursor:pointer;
  transition:transform .15s ease,opacity .2s ease,background .2s ease;
  text-decoration:none;
  display:inline-flex;
  align-items:center;
  justify-content:center;
}
button:hover, .link-btn:hover{transform:translateY(-1px);}
.btn-primary{
  background:var(--forest-900);
  color:var(--white);
}
.btn-primary:hover{background:var(--forest-700);}
.btn-secondary, .link-btn.secondary{
  background:var(--white);
  color:var(--forest-900);
  border:1px solid var(--forest-700);
}
.btn-secondary:hover, .link-btn.secondary:hover{background:var(--sage-100);}
.link-btn.primary{
  background:var(--forest-900);
  color:var(--white);
}
.link-btn.primary:hover{
  background:var(--forest-700);
}
.result{
  display:none;
  margin-top:20px;
  border-top:1px solid var(--line);
  padding-top:20px;
}
.result.show{display:block;}
.result-box{
  background:var(--white);
  border:1px solid var(--line);
  border-radius:16px;
  padding:20px;
}
.result-kicker{
  color:var(--forest-700);
  font-size:.9rem;
  font-weight:700;
  text-transform:uppercase;
  letter-spacing:.04em;
  margin-bottom:6px;
}
.result-title{
  font-size:1.45rem;
  color:var(--forest-900);
  margin:0 0 8px;
  font-weight:750;
}
.result-text{
  margin:0 0 10px;
  color:var(--forest-900);
}
.breath-visual{
  margin-top:10px;
  padding:18px 12px 12px;
  background:linear-gradient(180deg,var(--sage-100) 0%, #f8fbf9 100%);
  border:1px solid var(--line);
  border-radius:16px;
  text-align:center;
}
.circle-wrap{
  display:flex;
  justify-content:center;
  align-items:center;
  min-height:220px;
}
.circle{
  width:150px;
  height:150px;
  border-radius:50%;
  background:radial-gradient(circle at 30% 30%, #4d7c6c 0%, var(--forest-700) 45%, var(--forest-900) 100%);
  display:flex;
  align-items:center;
  justify-content:center;
  color:var(--white);
  text-align:center;
  font-weight:700;
  padding:14px;
  box-shadow:0 18px 36px rgba(23,61,51,.22);
  transform:scale(1);
  transition:transform 1s linear;
  will-change:transform;
}
.circle span{
  display:block;
  font-size:1rem;
  line-height:1.35;
}
.phase{
  margin-top:8px;
  font-size:.95rem;
  color:var(--muted);
  min-height:24px;
}
.pattern{
  margin-top:8px;
  color:var(--forest-800);
  font-weight:700;
}
.script{
  margin-top:14px;
  padding:14px 16px;
  border-radius:12px;
  background:var(--sage-100);
  color:var(--forest-900);
  font-size:.96rem;
  border:1px solid var(--sage-300);
}
.info-grid{
  display:grid;
  grid-template-columns:1fr;
  gap:12px;
  margin-top:14px;
}
.info-box{
  padding:14px 16px;
  border-radius:12px;
  border:1px solid var(--line);
  background:var(--soft);
}
.info-box h4{
  margin:0 0 8px;
  font-size:.95rem;
  color:var(--forest-900);
}
.cta-block{
  margin-top:18px;
  padding:16px;
  border-radius:14px;
  border:1px solid var(--line);
  background:linear-gradient(180deg,#fafcfb 0%, var(--soft) 100%);
}
.cta-copy{
  margin:0 0 12px;
  font-size:.96rem;
}
.cta-buttons{
  display:flex;
  flex-wrap:wrap;
  gap:10px;
}
.footer-note{
  margin-top:12px;
  font-size:.86rem;
}
.legal{
  margin-top:24px;
  font-size:.82rem;
  text-align:center;
}
.legal a{
  color:var(--muted);
  text-decoration:none;
}
.legal a:hover{
  text-decoration:underline;
}
.github-note{
  margin-top:18px;
  padding:14px 16px;
  border-radius:12px;
  background:#fafcfb;
  border:1px dashed var(--line);
  color:var(--muted);
  font-size:.92rem;
}
code{
  background:#edf4ef;
  color:var(--forest-900);
  padding:2px 6px;
  border-radius:6px;
  font-family:ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,monospace;
}
@media(max-width:980px){
  .option-grid.goal-grid{grid-template-columns:repeat(3,minmax(0,1fr));}
}
@media(max-width:760px){
  .wrap{padding:16px 14px 32px;}
  .option-grid,.option-grid.three,.option-grid.goal-grid,.cta-buttons{grid-template-columns:1fr;}
  .card{padding:18px;}
  .logo-slot{
    width:64px;
    height:64px;
    border-radius:14px;
  }
  .circle{
    width:132px;
    height:132px;
  }
  .circle-wrap{min-height:200px;}
  .cta-buttons{
    display:grid;
  }
}
@media (prefers-reduced-motion: reduce){
  html{scroll-behavior:auto;}
  *,*::before,*::after{
    animation:none !important;
    transition:none !important;
  }
}
</style>
</head>
<body>
<div class="wrap">

  <section class="hero">
    <div class="brand-row">
      <div class="logo-slot">
        <img src="./assets/lebensluft-logo.png" alt="Lebensluft Logo" id="brandLogo" />
        <div class="logo-placeholder" id="logoPlaceholder">LOGO</div>
      </div>
      <div>
        <div class="eyebrow">Lebensluft · Breathwork in Frankfurt</div>
        <h1>Finde die Atemübung, die zu deinem Moment passt</h1>
      </div>
    </div>
    <p class="intro">Ruhig, alltagstauglich und an deinen Zustand angepasst – für Stress, Fokus, Meetings, Übergänge, Schlaf oder neue Energie.</p>
    <p class="disclaimer">Hinweis: Dieses Tool ersetzt keine medizinische Beratung. Bei Brustschmerz, Atemnot, Schwindel oder starkem Unwohlsein bitte nur sanft atmen und keine Atempausen machen.</p>
  </section>

  <section class="card">
    <h2>Deine Empfehlung</h2>

    <div class="question">
      <div class="question-title">Was brauchst du gerade?</div>
      <div class="option-grid goal-grid">
        <div class="option"><input type="radio" id="goal-stress" name="goal" value="stress" checked><label for="goal-stress">Stress regulieren</label></div>
        <div class="option"><input type="radio" id="goal-reset" name="goal" value="reset"><label for="goal-reset">Kurz resetten</label></div>
        <div class="option"><input type="radio" id="goal-meeting-start" name="goal" value="meeting-start"><label for="goal-meeting-start">Vor einem Meeting</label></div>
        <div class="option"><input type="radio" id="goal-meeting-end" name="goal" value="meeting-end"><label for="goal-meeting-end">Nach einem Meeting</label></div>
        <div class="option"><input type="radio" id="goal-focus" name="goal" value="focus"><label for="goal-focus">Fokus finden</label></div>
        <div class="option"><input type="radio" id="goal-energy" name="goal" value="energy"><label for="goal-energy">Energie aktivieren</label></div>
        <div class="option"><input type="radio" id="goal-presentation" name="goal" value="presentation"><label for="goal-presentation">Vor einem Auftritt</label></div>
        <div class="option"><input type="radio" id="goal-call" name="goal" value="call"><label for="goal-call">Zwischen zwei Calls</label></div>
        <div class="option"><input type="radio" id="goal-overload" name="goal" value="overload"><label for="goal-overload">Mentale Überlastung</label></div>
        <div class="option"><input type="radio" id="goal-sleep" name="goal" value="sleep"><label for="goal-sleep">Vor dem Schlafen</label></div>
        <div class="option"><input type="radio" id="goal-thoughts" name="goal" value="thoughts"><label for="goal-thoughts">Gedanken beruhigen</label></div>
      </div>
    </div>

    <div class="question">
      <div class="question-title">Soll es unauffällig sein?</div>
      <div class="option-grid">
        <div class="option"><input type="radio" id="subtle-yes" name="subtle" value="yes"><label for="subtle-yes">Ja, office-tauglich</label></div>
        <div class="option"><input type="radio" id="subtle-no" name="subtle" value="no" checked><label for="subtle-no">Nein, egal</label></div>
      </div>
    </div>

    <details>
      <summary>Personalisieren</summary>
      <div class="details-inner">
        <p class="help">Optional: Mit einem kurzen Breath-Check wird die Übung an deine aktuelle Atemruhe angepasst.</p>

        <div class="question">
          <div class="question-title">Sicherheit</div>
          <div class="option-grid">
            <div class="option"><input type="radio" id="safe-ok" name="safety" value="ok" checked><label for="safe-ok">Fühlt sich gerade okay an</label></div>
            <div class="option"><input type="radio" id="safe-no" name="safety" value="no"><label for="safe-no">Bitte ohne Atemanhalten</label></div>
          </div>
          <div class="inline-note">Wenn du dich unruhig, schwindelig oder kurzatmig fühlst, nutze lieber Varianten ohne Pause.</div>
        </div>

        <div class="question">
          <div class="question-title">CO₂-Toleranz / Breath Check</div>
          <p class="help">Nach einer normalen Ausatmung die Nase sanft zuhalten und beim ersten klaren Atemimpuls stoppen – nicht maximal halten.</p>
          <div class="option-grid three">
            <div class="option"><input type="radio" id="cp-low" name="cp" value="low"><label for="cp-low">Unter 20 Sek.</label></div>
            <div class="option"><input type="radio" id="cp-mid" name="cp" value="mid" checked><label for="cp-mid">20–30 Sek.</label></div>
            <div class="option"><input type="radio" id="cp-high" name="cp" value="high"><label for="cp-high">Über 30 Sek.</label></div>
          </div>
        </div>
      </div>
    </details>

    <div class="actions">
      <button class="btn-primary" id="findBtn">Atemübung finden</button>
    </div>

    <div class="result" id="result">
      <div class="result-box">
        <div class="result-kicker">Empfehlung von Lebensluft</div>
        <h3 class="result-title" id="resultTitle">Verlängerte Ausatmung</h3>
        <p class="result-text" id="resultText"></p>
        <p class="result-reason" id="resultReason"></p>

        <div class="breath-visual">
          <div class="circle-wrap">
            <div class="circle" id="breathCircle"><span id="circleText">Bereit</span></div>
          </div>
          <div class="phase" id="phaseText">Gleich geht’s los</div>
          <div class="pattern" id="patternText">4 Sek. ein · 6 Sek. aus</div>
          <div class="office-note" id="officeNote"></div>
        </div>

        <div class="script" id="scriptText"></div>

        <div class="info-grid">
          <div class="info-box">
            <h4>Warum das helfen kann</h4>
            <div class="science-copy" id="scienceText"></div>
          </div>
        </div>

        <div class="actions" style="margin-top:16px;">
          <button class="btn-secondary" id="altBtn">Alternative zeigen</button>
          <button class="btn-secondary" id="gentleBtn">Sanftere Variante</button>
        </div>

        <div class="cta-block">
          <p class="cta-copy">Ich unterstütze dich, dein Team oder dein Unternehmen dabei, Breathwork fest im Alltag zu verankern. [web:2]</p>
          <div class="cta-buttons">
            <a class="link-btn primary" href="https://www.lebensluft.net/" target="_blank" rel="noopener noreferrer">Zu Lebensluft</a>
            <a class="link-btn secondary" href="https://calendly.com/lebensluft-breathwork/erstgesprach-fur-unternehmen-clone" target="_blank" rel="noopener noreferrer">Für Privatpersonen: Unverbindliches Beratungsgespräch buchen</a>
            <a class="link-btn secondary" href="https://calendly.com/lebensluft-breathwork/oprm-einordnung-clone" target="_blank" rel="noopener noreferrer">Für Unternehmen: Unverbindliches Beratungsgespräch buchen</a>
          </div>
        </div>

        <div class="footer-note">Atme immer weich und ohne Druck. Wenn etwas unangenehm wird, kehre zu deinem natürlichen Atem zurück.</div>

        <div class="github-note">
          <strong>Logo in GitHub einfügen:</strong> Lege im selben Repository einen Ordner <code>assets</code> an und speichere dein Logo als <code>lebensluft-logo.png</code>. Der Pfad in dieser Datei ist bereits auf <code>./assets/lebensluft-logo.png</code> gesetzt. [web:60]
        </div>
      </div>
    </div>

    <div class="legal">
      <a href="https://www.lebensluft.net/impressum" target="_blank" rel="noopener noreferrer">Impressum</a> [web:69]
    </div>
  </section>
</div>

<script>
const resultEl=document.getElementById("result");
const resultTitle=document.getElementById("resultTitle");
const resultText=document.getElementById("resultText");
const resultReason=document.getElementById("resultReason");
const patternText=document.getElementById("patternText");
const scriptText=document.getElementById("scriptText");
const phaseText=document.getElementById("phaseText");
const scienceText=document.getElementById("scienceText");
const officeNote=document.getElementById("officeNote");
const circleText=document.getElementById("circleText");
const breathCircle=document.getElementById("breathCircle");
const findBtn=document.getElementById("findBtn");
const altBtn=document.getElementById("altBtn");
const gentleBtn=document.getElementById("gentleBtn");
const brandLogo=document.getElementById("brandLogo");
const logoPlaceholder=document.getElementById("logoPlaceholder");

let currentPair=[];
let breathTimeouts=[];

brandLogo.addEventListener("load",()=>{
  brandLogo.style.display="block";
  logoPlaceholder.style.display="none";
});
brandLogo.addEventListener("error",()=>{
  brandLogo.style.display="none";
  logoPlaceholder.style.display="flex";
});

const scienceMap={
  slowExhale:[
    "Eine längere Ausatmung kann dem Körper helfen, von Anspannung Schritt für Schritt in mehr Ruhe zu wechseln.",
    "Wenn du etwas länger ausatmest, fällt Loslassen vielen Menschen leichter."
  ],
  coherent:[
    "Ein gleichmäßiger Atemrhythmus kann helfen, innerlich ruhiger und klarer zu werden.",
    "Wenn Ein- und Ausatmung ruhig und gleichmäßig werden, fühlt sich der Atem oft stabiler an."
  ],
  physioSigh:[
    "Diese Übung kann helfen, einen akuten Stressmoment etwas schneller abzufangen.",
    "Der lange Ausatemteil kann sich wie ein kurzes inneres Durchatmen anfühlen."
  ],
  observe:[
    "Schon das bewusste Wahrnehmen des Atems kann helfen, aus dem Gedankenkarussell auszusteigen.",
    "Du musst nichts perfekt machen – oft hilft es schon, dem Atem kurz Aufmerksamkeit zu geben."
  ],
  movement:[
    "Kleine Bewegungen zusammen mit dem Atem können helfen, Spannung leichter abzubauen.",
    "Wenn der Körper mitmachen darf, fällt es vielen Menschen leichter, wieder bei sich anzukommen."
  ]
};

const techniques={
  stress:[
    {name:"Verlängerte Ausatmung",style:"calm",category:"calm",subtle:true,officeSafe:true,science:"slowExhale",text:"Diese Übung passt gut, wenn du Anspannung lösen und ruhiger werden möchtest.",reason:"Sie ist einfach, leise und alltagstauglich.",script:"Atme ruhig durch die Nase ein und etwas länger aus. Lass Schultern und Kiefer weich werden."},
    {name:"5–7 Atmung",style:"deep-calm",category:"calm",subtle:true,officeSafe:true,science:"slowExhale",text:"Diese Variante bringt noch etwas mehr Ruhe in deinen Atemrhythmus.",reason:"Gut, wenn du eine klar spürbare Beruhigung suchst.",script:"Atme ruhig durch die Nase ein und weich länger aus. Ohne Druck."},
    {name:"Physiologischer Seufzer",style:"sigh",category:"calm",subtle:false,officeSafe:false,science:"physioSigh",text:"Diese Übung kann bei akutem Druck kurzfristig entlasten.",reason:"Hilfreich bei plötzlich hoher Anspannung.",script:"Einmal einatmen, einen kleinen zweiten Einatemzug ergänzen und dann langsam ausatmen."}
  ],
  reset:[
    {name:"3 ruhige Atemzüge",style:"calm-short",category:"reset",subtle:true,officeSafe:true,science:"slowExhale",text:"Eine kurze, schlichte Übung für einen kleinen Neustart.",reason:"Sie ist schnell und unkompliziert.",script:"Nimm drei ruhige Atemzüge. Mit jeder Ausatmung darf etwas Spannung abfließen."},
    {name:"Atem beobachten",style:"observe",category:"awareness",subtle:true,officeSafe:true,science:"observe",text:"Diese Übung holt die Aufmerksamkeit zurück in den Körper.",reason:"Gut, wenn du erst einmal nur ankommen willst.",script:"Beobachte deinen Atem für 30 bis 60 Sekunden, ohne etwas zu verändern."},
    {name:"Walking breath",style:"walking",category:"movement",subtle:false,officeSafe:false,science:"movement",text:"Diese Übung verbindet Gehen mit einem ruhigen Atemrhythmus.",reason:"Hilfreich, wenn Sitzen gerade nicht regulierend wirkt.",script:"Gehe langsam. Atme über wenige Schritte ein und über etwas mehr Schritte aus."}
  ],
  "meeting-start":[
    {name:"Meeting-Ankommen",style:"meeting-calm",category:"focus",subtle:true,officeSafe:true,science:"slowExhale",text:"Eine leise, unauffällige Atemübung vor dem Gespräch.",reason:"Vor Meetings funktionieren diskrete Rhythmen oft am besten.",script:"Atme ruhig ein und etwas länger aus. Die Ausatmung bleibt leise und weich."},
    {name:"Kohärente Atmung",style:"coherent",category:"focus",subtle:true,officeSafe:true,science:"coherent",text:"Diese Übung schafft einen stabilen Rhythmus für Präsenz und Fokus.",reason:"Gut, wenn du ruhig und klar in ein Gespräch gehen willst.",script:"Atme gleichmäßig ein und aus. Bleibe aufrecht und entspannt."},
    {name:"Finger Tracing",style:"finger",category:"grounding",subtle:true,officeSafe:true,science:"movement",text:"Kleine Handbewegung plus Atemfokus für mehr Sammlung.",reason:"Die feine Bewegung gibt dem Geist einen Anker.",script:"Fahre mit einem Finger die andere Hand entlang – hoch beim Einatmen, runter beim Ausatmen."}
  ],
  "meeting-end":[
    {name:"Calm close",style:"calm",category:"calm",subtle:true,officeSafe:true,science:"slowExhale",text:"Eine Übung, um nach einem Termin bewusst loszulassen.",reason:"Hilfreich für einen klareren Übergang.",script:"Atme normal ein und etwas länger aus. Nutze drei bis fünf ruhige Atemzüge als Abschluss."},
    {name:"3 Ausatemzüge",style:"calm-short",category:"calm",subtle:true,officeSafe:true,science:"slowExhale",text:"Kurz, diskret und wirksam nach intensiven Gesprächen.",reason:"Gut bei engem Takt.",script:"Atme drei Mal ruhig ein und etwas länger aus."}
  ],
  focus:[
    {name:"Kohärente Atmung",style:"coherent",category:"focus",subtle:true,officeSafe:true,science:"coherent",text:"Diese Übung unterstützt ruhige Wachheit und mentale Stabilität.",reason:"Ein ausgeglichener Rhythmus hilft oft mehr als zu viel Druck.",script:"Atme gleichmäßig ein und aus. Ruhig, leise und ohne Druck."},
    {name:"Klarer Rhythmus",style:"balance",category:"focus",subtle:true,officeSafe:true,science:"coherent",text:"Eine strukturierte Atemübung für mehr mentale Ordnung.",reason:"Gut, wenn du dich sortieren möchtest.",script:"Atme in einem gleichmäßigen Rhythmus und lass den Atem weich bleiben."},
    {name:"Finger Tracing",style:"finger",category:"grounding",subtle:true,officeSafe:true,science:"movement",text:"Atem plus kleine Bewegung als Aufmerksamkeitsanker.",reason:"Besonders hilfreich bei einem vollen Kopf.",script:"Beim Hochstreichen einatmen, beim Runterstreichen ausatmen."}
  ],
  energy:[
    {name:"Aktivierende Nasenatmung",style:"energy",category:"energy",subtle:true,officeSafe:true,science:"coherent",text:"Eine kontrollierte, etwas präsentere Nasenatmung für neue Wachheit.",reason:"Gut, wenn du einen kurzen Energieimpuls suchst.",script:"Atme etwas aktiver, aber weiter ruhig durch die Nase. Bleibe aufrecht."},
    {name:"Reach & breathe",style:"reach",category:"energy",subtle:false,officeSafe:false,science:"movement",text:"Eine aktivierende Übung mit Armbewegung und Rhythmus.",reason:"Gut, wenn du körperlich wacher werden möchtest.",script:"Atme ein, während du die Arme hebst. Atme aus, während du sie wieder senkst."},
    {name:"Calm energy",style:"balance",category:"focus",subtle:true,officeSafe:true,science:"coherent",text:"Mehr Klarheit ohne Überstimulation.",reason:"Praktisch, wenn du Energie und Ruhe zugleich brauchst.",script:"Atme gleichmäßig und etwas präsenter, aber nicht hektisch."}
  ],
  presentation:[
    {name:"Presentation reset",style:"calm",category:"calm",subtle:true,officeSafe:true,science:"slowExhale",text:"Hilft, Nervosität zu senken, ohne dich schläfrig zu machen.",reason:"Vor Auftritten ist ruhige Regulierung oft hilfreich.",script:"Atme ruhig ein und länger aus. Lass Kiefer, Bauch und Schultern weich werden."},
    {name:"Steady presence",style:"coherent",category:"focus",subtle:true,officeSafe:true,science:"coherent",text:"Ein klarer Rhythmus für Ruhe und Präsenz.",reason:"Gut, wenn du geerdet und wach sein willst.",script:"Atme gleichmäßig ein und aus und richte dich innerlich auf."},
    {name:"Physiologischer Seufzer",style:"sigh",category:"calm",subtle:false,officeSafe:false,science:"physioSigh",text:"Kann eine akute Nervositätsspitze kurz entschärfen.",reason:"Eher für den unmittelbaren Moment.",script:"Ein doppelter Einatemzug, dann eine lange weiche Ausatmung."}
  ],
  call:[
    {name:"Call reset",style:"calm-short",category:"reset",subtle:true,officeSafe:true,science:"slowExhale",text:"Eine kleine Zwischen-Übung, um sauber in den nächsten Call zu wechseln.",reason:"Ideal bei engem Takt.",script:"Atme drei bis fünf Mal ruhig ein und etwas länger aus."},
    {name:"Atem beobachten",style:"observe",category:"awareness",subtle:true,officeSafe:true,science:"observe",text:"Für einen stillen Reset ohne zusätzliche Steuerung.",reason:"Gut nach viel Input.",script:"Beobachte den Atem für einen Moment und lass ihn von selbst kommen und gehen."}
  ],
  overload:[
    {name:"Atem beobachten",style:"observe",category:"awareness",subtle:true,officeSafe:true,science:"observe",text:"Weniger tun, mehr wahrnehmen – gut bei mentaler Überlastung.",reason:"Wenn ohnehin viel los ist, hilft oft etwas Einfaches am meisten.",script:"Beobachte deinen Atem 30 bis 60 Sekunden lang."},
    {name:"Finger Tracing",style:"finger",category:"grounding",subtle:true,officeSafe:true,science:"movement",text:"Berührung, Rhythmus und Atem bündeln die Aufmerksamkeit.",reason:"Gut, wenn der Kopf zu voll wirkt.",script:"Streiche langsam Finger für Finger entlang und verbinde es mit Ein- und Ausatmung."},
    {name:"3 ruhige Atemzüge",style:"calm-short",category:"reset",subtle:true,officeSafe:true,science:"slowExhale",text:"Ein kleiner Anker ohne viel Aufwand.",reason:"Schnell und unkompliziert.",script:"Drei ruhige Atemzüge, mit etwas längerer Ausatmung."}
  ],
  sleep:[
    {name:"Sleep exhale",style:"sleep",category:"sleep",subtle:true,officeSafe:true,allowPause:true,science:"slowExhale",text:"Eine weiche Abendübung mit längerer Ausatmung.",reason:"Für Schlaf passt oft ein sanfter, verlangsamter Rhythmus.",script:"Ruhig einatmen und deutlich länger ausatmen. Nur wenn es angenehm ist, darf nach der Ausatmung ein kleiner stiller Moment entstehen."},
    {name:"4–6 Abendatmung",style:"sleep-soft",category:"sleep",subtle:true,officeSafe:true,allowPause:false,science:"slowExhale",text:"Eine mildere Abendvariante ohne lange Atemhaltephasen.",reason:"Gut, wenn du es abends besonders weich möchtest.",script:"Atme weich durch die Nase ein und länger aus. Kein Zwang, keine Leistung."},
    {name:"Soft breath awareness",style:"observe",category:"sleep",subtle:true,officeSafe:true,science:"observe",text:"Wenn du abends nichts mehr steuern möchtest.",reason:"Entlastend, wenn aktive Technik Druck macht.",script:"Lege eine Hand auf Brust oder Bauch und beobachte deinen Atem, ohne ihn zu verändern."}
  ],
  thoughts:[
    {name:"Raum durch Ausatmung",style:"thoughts",category:"calm",subtle:true,officeSafe:true,allowPause:true,science:"slowExhale",text:"Hilft, Gedankendruck zu verringern und etwas mehr inneren Raum zu spüren.",reason:"Eine längere Ausatmung ist oft einfacher als komplizierte Muster.",script:"Atme ruhig ein und länger aus. Stell dir vor, mit jeder Ausatmung wird es innen etwas weiter."},
    {name:"Atem zählen",style:"counting",category:"focus",subtle:true,officeSafe:true,science:"observe",text:"Gibt dem Geist eine kleine, klare Aufgabe.",reason:"Hilfreich bei Gedankenkreisen.",script:"Zähle die Ausatmungen von 1 bis 10 und beginne dann wieder bei 1."},
    {name:"Finger Tracing",style:"finger",category:"grounding",subtle:true,officeSafe:true,science:"movement",text:"Körperlicher Anker für einen überaktiven Kopf.",reason:"Die kleine Bewegung hilft, Aufmerksamkeit zu bündeln.",script:"Finger für Finger hoch und runter streichen, passend zu Ein- und Ausatmung."}
  ]
};

function getValue(name){
  const checked=document.querySelector(`input[name="${name}"]:checked`);
  return checked?checked.value:null;
}

function randomItem(arr){
  return arr[Math.floor(Math.random()*arr.length)];
}

function pickScienceText(scienceKey){
  const pool=scienceMap[scienceKey] || ["Diese Übung kann helfen, den Atem ruhiger und angenehmer werden zu lassen."];
  return randomItem(pool);
}

function timingFor(style,cp,safety,allowPause){
  let inhale=4, exhale=5, pause=0;

  if(style==="calm"){inhale=4;exhale=6;}
  if(style==="deep-calm"){inhale=5;exhale=7;}
  if(style==="calm-short"){inhale=3;exhale=4;}
  if(style==="meeting-calm"){inhale=4;exhale=5;}
  if(style==="coherent"){inhale=5;exhale=5;}
  if(style==="balance"){inhale=4;exhale=4;}
  if(style==="energy"){inhale=3;exhale=3;}
  if(style==="reach"){inhale=3;exhale=3;}
  if(style==="sleep"){inhale=4;exhale=6;}
  if(style==="sleep-soft"){inhale=4;exhale=6;}
  if(style==="thoughts"){inhale=4;exhale=6;}
  if(style==="counting"){inhale=4;exhale=5;}
  if(style==="walking"){inhale=3;exhale=4;}
  if(style==="finger"){inhale=4;exhale=4;}
  if(style==="sigh"){inhale=2;exhale=6;}

  if(cp==="low"){
    inhale=Math.max(2, inhale-1);
    exhale=Math.max(inhale, exhale-1);
    pause=0;
  }
  if(cp==="mid"){
    if(allowPause && safety==="ok" && (style==="sleep" || style==="thoughts")) pause=1;
  }
  if(cp==="high"){
    inhale=inhale+1;
    exhale=exhale+1;
    if(allowPause && safety==="ok" && (style==="sleep" || style==="thoughts")) pause=2;
  }
  if(safety==="no") pause=0;

  return {inhale,exhale,pause};
}

function movementLabelFor(style){
  if(style==="walking") return {inLabel:"Gehen + ein",outLabel:"Gehen + aus",inShort:"Ein",outShort:"Aus"};
  if(style==="finger") return {inLabel:"Hochstreichen",outLabel:"Runterstreichen",inShort:"Ein",outShort:"Aus"};
  if(style==="reach") return {inLabel:"Arme heben",outLabel:"Arme senken",inShort:"Ein",outShort:"Aus"};
  return {inLabel:"Einatmen",outLabel:"Ausatmen",inShort:"Ein",outShort:"Aus"};
}

function personalizeTechnique(tech){
  const cp=getValue("cp")||"mid";
  const safety=getValue("safety")||"ok";
  const subtle=getValue("subtle")||"no";
  const t=timingFor(tech.style,cp,safety,tech.allowPause);
  let office="";

  if(subtle==="yes"){
    office=tech.officeSafe
      ? "Diese Variante ist leise und meist gut im Büro machbar."
      : "Diese Variante ist eher nicht office-tauglich, weil sie auffälliger sein kann.";
  }

  if(tech.style==="observe"){
    return {
      ...tech,
      pattern:"Natürliche Atmung",
      sequence:[{label:"Beobachten",short:"Ruhe",seconds:4,scale:1}],
      script:tech.script+" Du musst nichts anhalten oder korrigieren.",
      office
    };
  }

  if(tech.style==="sigh"){
    const exhale=cp==="low"?4:cp==="high"?7:6;
    return {
      ...tech,
      pattern:`2 Einatemzüge · ${exhale} Sek. aus`,
      sequence:[
        {label:"Einatmen",short:"Ein",seconds:2,scale:1.06},
        {label:"Kleiner zweiter Einatemzug",short:"+Ein",seconds:1,scale:1.14},
        {label:"Lange Ausatmung",short:"Aus",seconds:exhale,scale:.88}
      ],
      script:tech.script+" Wenn dein Atemreiz früh kommt, halte die Ausatmung kürzer und ganz weich.",
      office
    };
  }

  const labels=movementLabelFor(tech.style);
  let sequence=[
    {label:labels.inLabel,short:labels.inShort,seconds:t.inhale,scale:1.12},
    {label:labels.outLabel,short:labels.outShort,seconds:t.exhale,scale:.86}
  ];

  if(t.pause>0){
    sequence.push({label:"Kurze Pause",short:"Pause",seconds:t.pause,scale:.84});
  }

  let pattern=`${t.inhale} Sek. ein · ${t.exhale} Sek. aus`;
  if(tech.style==="walking") pattern=`${t.inhale} Schritte ein · ${t.exhale} Schritte aus`;
  if(tech.style==="finger") pattern=`Hoch beim Einatmen · runter beim Ausatmen`;
  if(t.pause>0) pattern+=` · ${t.pause} Sek. Pause`;

  let extra="";
  if(cp==="low") extra+=" Deine CO₂-Toleranz ist heute eher niedriger, deshalb bleibt der Rhythmus kürzer und weicher.";
  if(cp==="mid") extra+=" Der Rhythmus ist als sanfte Standardvariante gewählt.";
  if(cp==="high") extra+=" Deine CO₂-Toleranz erlaubt heute einen etwas längeren, ruhigeren Rhythmus.";
  if(safety==="no") extra+=" Atempausen sind ausgeschlossen.";

  return {
    ...tech,
    pattern,
    sequence,
    script:tech.script+extra,
    office
  };
}

function filterForPreferences(list){
  const subtle=getValue("subtle");
  const cp=getValue("cp")||"mid";
  const safety=getValue("safety")||"ok";
  let filtered=[...list];

  if(subtle==="yes"){
    filtered=filtered.filter(t=>t.officeSafe===true && t.subtle===true);
  }

  if(cp==="low"){
    filtered=filtered.filter(t=>t.style!=="sigh" || getValue("goal")==="presentation");
  }

  if(safety==="no"){
    filtered=filtered.map(t=>({...t,allowPause:false}));
  }

  if(filtered.length===0){
    filtered=[...list].filter(t=>t.subtle===true);
  }

  if(filtered.length===0){
    filtered=[techniques.reset[0], techniques.reset[1]];
  }

  return filtered;
}

function sortByGoalLogic(goal,list){
  const priorities={
    stress:["calm","deep-calm","calm-short","observe","sigh"],
    sleep:["sleep-soft","sleep","observe"],
    focus:["coherent","balance","finger"],
    "meeting-start":["meeting-calm","coherent","finger"],
    energy:["energy","balance","reach"],
    overload:["observe","finger","calm-short"],
    thoughts:["thoughts","counting","finger"],
    reset:["calm-short","observe","walking"],
    call:["calm-short","observe"],
    "meeting-end":["calm","calm-short"],
    presentation:["coherent","calm","sigh"]
  };
  const priority=priorities[goal]||[];
  return list.sort((a,b)=>{
    const ai=priority.indexOf(a.style);
    const bi=priority.indexOf(b.style);
    return (ai===-1?99:ai)-(bi===-1?99:bi);
  });
}

function pickTechniques(goalOverride=null){
  const goal=goalOverride || getValue("goal");
  let list=[...(techniques[goal]||techniques.stress)];
  list=filterForPreferences(list);
  list=sortByGoalLogic(goal,list);
  return list.map(personalizeTechnique);
}

function renderTechnique(tech){
  resultTitle.textContent=tech.name;
  resultText.textContent=tech.text;
  resultReason.textContent=tech.reason;
  patternText.textContent=tech.pattern;
  scriptText.textContent=tech.script;
  scienceText.textContent=pickScienceText(tech.science);
  officeNote.textContent=tech.office || "";
  resultEl.classList.add("show");
  startBreathingAnimation(tech.sequence);
}

function clearBreathTimers(){
  breathTimeouts.forEach(t=>clearTimeout(t));
  breathTimeouts.forEach(t=>clearInterval(t));
  breathTimeouts=[];
}

function runPhase(sequence,index){
  const phase=sequence[index];
  phaseText.textContent=phase.label;
  breathCircle.style.transition=`transform ${phase.seconds}s linear`;
  breathCircle.style.transform=`scale(${phase.scale})`;

  let remaining=phase.seconds;
  circleText.innerHTML=`${phase.short}<br>${remaining}`;

  const countdown=setInterval(()=>{
    remaining--;
    if(remaining>0){
      circleText.innerHTML=`${phase.short}<br>${remaining}`;
    }else{
      clearInterval(countdown);
      circleText.innerHTML=`${phase.short}<br>0`;
    }
  },1000);

  breathTimeouts.push(countdown);

  const next=setTimeout(()=>{
    clearInterval(countdown);
    runPhase(sequence,(index+1)%sequence.length);
  },phase.seconds*1000);

  breathTimeouts.push(next);
}

function startBreathingAnimation(sequence){
  clearBreathTimers();
  breathCircle.style.transition="none";
  breathCircle.style.transform="scale(1)";
  circleText.innerHTML="Bereit";
  phaseText.textContent="Gleich geht’s los";

  const starter=setTimeout(()=>{
    runPhase(sequence,0);
  },250);

  breathTimeouts.push(starter);
}

findBtn.addEventListener("click",()=>{
  currentPair=pickTechniques();
  renderTechnique(currentPair[0]);
  resultEl.scrollIntoView({behavior:"smooth",block:"start"});
});

altBtn.addEventListener("click",()=>{
  if(currentPair.length>1){
    currentPair.push(currentPair.shift());
    renderTechnique(currentPair[0]);
  }
});

gentleBtn.addEventListener("click",()=>{
  const gentleChoice=personalizeTechnique(techniques.reset[1]);
  renderTechnique(gentleChoice);
});
</script>
</body>
</html>
