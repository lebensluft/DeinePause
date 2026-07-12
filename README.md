<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
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
--muted:#587065;
--line:#cfd9d3;
--soft:#f4f8f5;
--shadow:0 10px 28px rgba(23,61,51,0.10);
--radius:16px;
--max:1140px;
}

*{box-sizing:border-box;}
body{
margin:0;
font-family:"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
background:linear-gradient(180deg,var(--cream) 0%, #f3f6f3 100%);
color:var(--text);
line-height:1.55;
}
.wrap{max-width:var(--max);margin:0 auto;padding:20px 20px 42px;}
.hero{
padding:10px 0 14px;
border-bottom:3px solid var(--forest-700);
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
font-size:clamp(2rem,5vw,3.2rem);
line-height:1.02;
margin:0 0 12px;
font-weight:750;
letter-spacing:-.03em;
color:var(--forest-900);
}
.intro,.disclaimer,.help,.inline-note,.footer-note,.result-reason,.science-copy,.fact-copy{
color:var(--muted);
}
.card{
background:rgba(255,255,255,.82);
backdrop-filter:blur(8px);
border:1px solid var(--line);
border-radius:var(--radius);
box-shadow:var(--shadow);
padding:22px;
margin-top:18px;
}
h2{font-size:1.35rem;margin:0 0 14px;color:var(--forest-900);}
.question{margin-bottom:14px;}
.question-title{font-size:1rem;font-weight:700;margin-bottom:8px;color:var(--forest-900);}
.option-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:10px;}
.option-grid.three{grid-template-columns:repeat(3,minmax(0,1fr));}
.option-grid.goal-grid{grid-template-columns:repeat(4,minmax(0,1fr));}
.option{position:relative;}
.option input{position:absolute;opacity:0;pointer-events:none;}
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
.option label:hover{border-color:var(--forest-700);background:var(--sage-100);}
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
.details-inner{padding:12px 16px 16px;border-top:1px solid var(--line);}
.actions{display:flex;gap:12px;flex-wrap:wrap;margin-top:14px;}
button{
appearance:none;border:none;border-radius:999px;padding:13px 22px;font-size:1rem;
font-weight:700;cursor:pointer;transition:transform .15s ease,opacity .2s ease,background .2s ease;
}
button:hover{transform:translateY(-1px);}
.btn-primary{background:var(--forest-900);color:var(--white);}
.btn-primary:hover{background:var(--forest-700);}
.btn-secondary{
background:var(--white);color:var(--forest-900);border:1px solid var(--forest-700);
}
.btn-secondary:hover{background:var(--sage-100);}
.result{display:none;margin-top:20px;border-top:1px solid var(--line);padding-top:20px;}
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
.result-title{font-size:1.45rem;color:var(--forest-900);margin:0 0 8px;font-weight:750;}
.result-text{margin:0 0 10px;color:var(--forest-900);}
.breath-visual{
margin-top:10px;
padding:18px 12px 12px;
background:linear-gradient(180deg,var(--sage-100) 0%, #f8fbf9 100%);
border:1px solid var(--line);
border-radius:16px;
text-align:center;
}
.figure-wrap{
display:flex;
justify-content:center;
align-items:center;
min-height:240px;
}
.figure-stage{
width:240px;
height:220px;
position:relative;
display:flex;
align-items:center;
justify-content:center;
}
.breath-glow{
position:absolute;
width:156px;
height:156px;
border-radius:50%;
background:radial-gradient(circle, rgba(59,114,95,.22) 0%, rgba(59,114,95,.08) 45%, rgba(59,114,95,0) 72%);
transform:scale(1);
transition:transform 1s linear;
}
.breath-person{
width:130px;
height:170px;
position:relative;
transform:scale(1);
transition:transform 1s linear;
}
.breath-person svg{width:100%;height:100%;display:block;}
.phase{margin-top:8px;font-size:.95rem;color:var(--muted);min-height:24px;}
.pattern{margin-top:8px;color:var(--forest-800);font-weight:700;}
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
grid-template-columns:repeat(2,minmax(0,1fr));
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
.fact-pill{
display:inline-block;
font-size:.78rem;
font-weight:700;
letter-spacing:.04em;
text-transform:uppercase;
padding:5px 9px;
border-radius:999px;
background:var(--sage-200);
color:var(--forest-900);
margin-bottom:8px;
}
.office-note{
margin-top:10px;
font-size:.9rem;
color:var(--muted);
}
.footer-note{margin-top:12px;font-size:.86rem;}
@media(max-width:980px){
.option-grid.goal-grid{grid-template-columns:repeat(3,minmax(0,1fr));}
}
@media(max-width:760px){
.wrap{padding:16px 14px 32px;}
.option-grid,.option-grid.three,.option-grid.goal-grid,.info-grid{grid-template-columns:1fr;}
.card{padding:18px;}
.figure-stage{width:200px;height:200px;}
}
</style>
</head>
<body>
<div class="wrap">
<section class="hero">
<div class="eyebrow">Lebensluft · Breathwork in Frankfurt</div>
<h1>Finde die Atemübung, die zu deinem Moment passt</h1>
<p class="intro">Ruhig, alltagstauglich und an deinen Zustand angepasst – für Stress, Fokus, Übergänge, Meetings, Regeneration oder neue Energie.</p>
<p class="disclaimer">Hinweis: Dieses Tool ersetzt keine medizinische Beratung. Bei Brustschmerz, starker Atemnot, Schwindel, Panik oder Schwangerschaft bitte keine Atempausen erzwingen und nur sanft üben.</p>
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

<details id="individualizeBox">
<summary>Personalisieren</summary>
<div class="details-inner">
<p class="help">Optional: Mit einem kurzen Breath-Check wird die Übung an deine aktuelle Atemruhe angepasst.</p>

<div class="question">
<div class="question-title">Sicherheit</div>
<div class="option-grid">
<div class="option"><input type="radio" id="safe-ok" name="safety" value="ok" checked><label for="safe-ok">Fühlt sich gerade okay an</label></div>
<div class="option"><input type="radio" id="safe-no" name="safety" value="no"><label for="safe-no">Bitte ohne Atemanhalten</label></div>
</div>
<div class="inline-note">Wenn du gerade unruhig, schwindelig oder sehr kurzatmig bist, nutze lieber Varianten ohne Pause.</div>
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
<h3 class="result-title" id="resultTitle">Extended exhale</h3>
<p class="result-text" id="resultText"></p>
<p class="result-reason" id="resultReason"></p>

<div class="breath-visual">
<div class="figure-wrap">
<div class="figure-stage">
<div class="breath-glow" id="breathGlow"></div>
<div class="breath-person" id="breathPerson">
<svg viewBox="0 0 140 180" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
<circle cx="70" cy="26" r="16" stroke="#173d33" stroke-width="4"/>
<path id="armsPath" d="M35 72 C48 62, 56 58, 70 58 C84 58, 92 62, 105 72" stroke="#173d33" stroke-width="4" stroke-linecap="round"/>
<path d="M70 42 V102" stroke="#173d33" stroke-width="4" stroke-linecap="round"/>
<path d="M70 102 L48 148" stroke="#173d33" stroke-width="4" stroke-linecap="round"/>
<path d="M70 102 L92 148" stroke="#173d33" stroke-width="4" stroke-linecap="round"/>
<path d="M42 78 L28 108" stroke="#173d33" stroke-width="4" stroke-linecap="round"/>
<path d="M98 78 L112 108" stroke="#173d33" stroke-width="4" stroke-linecap="round"/>
</svg>
</div>
</div>
</div>
<div class="phase" id="phaseText">Gleich geht’s los</div>
<div class="pattern" id="patternText">4 Sek. ein · 6 Sek. aus</div>
<div class="office-note" id="officeNote"></div>
</div>

<div class="script" id="scriptText"></div>

<div class="info-grid">
<div class="info-box">
<h4>Warum das wirkt</h4>
<div class="science-copy" id="scienceText"></div>
</div>
<div class="info-box">
<div class="fact-pill">Breathwork-Fact des Tages</div>
<div class="fact-copy" id="factText"></div>
</div>
</div>

<div class="actions" style="margin-top:16px;">
<button class="btn-secondary" id="altBtn">Alternative zeigen</button>
</div>

<div class="footer-note">Atme immer weich und ohne Druck. Wenn etwas unangenehm wird, kehre zu deinem natürlichen Atem zurück.</div>
</div>
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
const factText=document.getElementById("factText");
const officeNote=document.getElementById("officeNote");
const breathGlow=document.getElementById("breathGlow");
const breathPerson=document.getElementById("breathPerson");
const findBtn=document.getElementById("findBtn");
const altBtn=document.getElementById("altBtn");

let currentPair=[];
let breathTimeouts=[];

const facts=[
"Du atmest pro Tag ungefähr 20.000 Mal – meist, ohne es zu merken.",
"Die Nase filtert, erwärmt und befeuchtet die Luft, bevor sie in die Lunge gelangt.",
"Eine längere Ausatmung ist oft ein einfacher Weg, dem Nervensystem Sicherheit zu signalisieren.",
"Langsamer atmen bedeutet nicht tiefer oder stärker atmen – oft ist sanfter besser.",
"Dein Zwerchfell ist der wichtigste Atemmuskel und arbeitet bei jedem Atemzug mit."
];

const scienceMap={
slowExhale:"Eine längere, ruhige Ausatmung kann die parasympathische Regulation unterstützen. Für langsame Atmung im Bereich von etwa 6 Atemzügen pro Minute zeigen Reviews Vorteile für vagal vermittelte HRV und Baroreflex-Funktion.",
coherent:"Gleichmäßige langsame Atmung kann Herz, Kreislauf und Atmung zeitlich stärker koppeln. In der Forschung wird das mit verbesserter cardiorespiratorischer Kohärenz und autonomer Regulation verbunden.",
physioSigh:"Der physiologische Seufzer wird genutzt, um akute Anspannung rasch zu entladen. Er eignet sich eher als kurzer Reset als als lange Übung.",
observe:"Interozeptive Aufmerksamkeit kann helfen, aus mentaler Übersteuerung herauszukommen, ohne den Atem sofort aktiv manipulieren zu müssen.",
movement:"Kleine rhythmische Bewegung plus Atemfokus kann die Aufmerksamkeit binden und Spannungsenergie besser ableiten."
};

const techniques={
stress:[
{name:"Verlängerte Ausatmung",style:"calm",category:"calm",subtle:true,officeSafe:true,science:"slowExhale",text:"Diese Übung passt gut, wenn du dein System beruhigen und Spannung abbauen möchtest.",reason:"Für Stress ist eine sanft verlängerte Ausatmung oft der einfachste Zugang zu mehr Ruhe, ohne den Atem zu forcieren.",script:"Atme leise durch die Nase ein und noch etwas länger aus. Lass Kiefer und Schultern weich werden."},
{name:"5–7 Atmung",style:"deep-calm",category:"calm",subtle:true,officeSafe:true,science:"slowExhale",text:"Diese Variante bringt noch etwas mehr Ruhe in deinen Atemrhythmus.",reason:"Gut, wenn du etwas mehr Zeit hast und eine klar spürbare Beruhigung suchst.",script:"Atme ruhig durch die Nase ein und weich länger aus. Der Atem soll fließen, nicht gedrückt werden."},
{name:"Physiologischer Seufzer",style:"sigh",category:"calm",subtle:false,officeSafe:false,science:"physioSigh",text:"Diese Übung kann bei akutem Druck kurzfristig entlasten.",reason:"Hilfreich bei plötzlich hoher Anspannung, aber eher für private Momente als fürs Büro.",script:"Einmal einatmen, einen kleinen zweiten Einatemzug ergänzen und dann langsam ausatmen. Nur wenige Wiederholungen."},
{name:"Summende Ausatmung",style:"hum",category:"calm",subtle:false,officeSafe:false,science:"slowExhale",text:"Diese Übung verbindet eine längere Ausatmung mit einem sanften Summen.",reason:"Das Summen verlängert oft automatisch die Ausatmung, ist aber nicht unauffällig.",script:"Atme durch die Nase ein und summe weich auf der Ausatmung aus."}
],
reset:[
{name:"3 ruhige Atemzüge",style:"calm-short",category:"reset",subtle:true,officeSafe:true,science:"slowExhale",text:"Eine kurze, schlichte Übung für einen kleinen Neustart.",reason:"Ideal zwischen Aufgaben, nach einem Gespräch oder als Mini-Pause.",script:"Nimm drei ruhige Atemzüge. Mit jeder Ausatmung darf etwas Anspannung abfließen."},
{name:"Shake & breathe",style:"shake",category:"movement",subtle:false,officeSafe:false,science:"movement",text:"Diese Übung kombiniert leichte Bewegung mit natürlichem Atem.",reason:"Gut, wenn du Spannung eher körperlich als nur mental spürst.",script:"Schüttle Hände, Arme und Schultern locker aus und lass den Atem natürlich mitlaufen."},
{name:"Walking breath",style:"walking",category:"movement",subtle:false,officeSafe:false,science:"movement",text:"Diese Übung verbindet Gehen mit einem ruhigen Atemrhythmus.",reason:"Hilfreich, wenn Sitzen sich gerade nicht regulierend anfühlt.",script:"Gehe langsam. Atme über wenige Schritte ein und über etwas mehr Schritte aus."},
{name:"Atem beobachten",style:"observe",category:"awareness",subtle:true,officeSafe:true,science:"observe",text:"Diese Übung holt die Aufmerksamkeit zurück in den Körper.",reason:"Besonders nützlich, wenn du gerade nichts steuern, sondern erst einmal nur ankommen willst.",script:"Beobachte deinen Atem für 30 bis 60 Sekunden, ohne etwas zu verändern."},
{name:"Schulterkreis-Atmung",style:"shoulder-roll",category:"movement",subtle:false,officeSafe:false,science:"movement",text:"Eine ruhige Mobilisationsübung für Übergänge.",reason:"Gut bei Bildschirmspannung und festem Nacken.",script:"Beim Einatmen Schultern sanft nach oben und hinten kreisen, beim Ausatmen sinken lassen."}
],
"meeting-start":[
{name:"Meeting-Ankommen",style:"meeting-calm",category:"focus",subtle:true,officeSafe:true,science:"slowExhale",text:"Eine leise, unauffällige Atemübung vor dem Gespräch.",reason:"Vor Meetings funktionieren einfache, diskrete Rhythmen meist am besten.",script:"Atme ruhig ein und etwas länger aus. Die Ausatmung bleibt leise und weich."},
{name:"Kohärente Atmung",style:"coherent",category:"focus",subtle:true,officeSafe:true,science:"coherent",text:"Diese Übung schafft einen stabilen Rhythmus für Präsenz und Fokus.",reason:"Gut, wenn du ruhig, klar und wach in ein Gespräch gehen willst.",script:"Atme gleichmäßig ein und aus. Bleibe aufrecht und entspannt."},
{name:"Finger Tracing",style:"finger",category:"grounding",subtle:true,officeSafe:true,science:"movement",text:"Kleine Handbewegung plus Atemfokus für mehr Sammlung.",reason:"Die feine Bewegung gibt dem Geist einen zusätzlichen Anker.",script:"Fahre mit einem Finger die andere Hand entlang – hoch beim Einatmen, runter beim Ausatmen."}
],
"meeting-end":[
{name:"Calm close",style:"calm",category:"calm",subtle:true,officeSafe:true,science:"slowExhale",text:"Eine Übung, um nach einem Termin bewusst loszulassen.",reason:"Hilfreich für einen klareren Übergang in die nächste Aufgabe.",script:"Atme normal ein und etwas länger aus. Nutze drei bis fünf ruhige Atemzüge als Abschluss."},
{name:"3 Ausatemzüge",style:"calm-short",category:"calm",subtle:true,officeSafe:true,science:"slowExhale",text:"Kurz, diskret und wirksam nach intensiven Gesprächen.",reason:"Gut, wenn direkt der nächste Termin folgt.",script:"Atme drei Mal ruhig ein und etwas länger aus."},
{name:"Steh-Auf-Reset",style:"stand-reset",category:"movement",subtle:false,officeSafe:false,science:"movement",text:"Für kurze Unterbrechungen mit mehr Körperbeteiligung.",reason:"Gut, wenn du nach dem Sitzen wieder in Bewegung kommen willst.",script:"Stell dich hin, richte dich beim Einatmen auf und lasse beim Ausatmen Spannung aus Armen und Schultern sinken."}
],
focus:[
{name:"Kohärente Atmung",style:"coherent",category:"focus",subtle:true,officeSafe:true,science:"coherent",text:"Diese Übung unterstützt ruhige Wachheit und mentale Stabilität.",reason:"Für Fokus ist ein ausgeglichener Rhythmus oft hilfreicher als sehr beruhigende oder aktivierende Muster.",script:"Atme gleichmäßig ein und aus. Ruhig, leise und ohne Druck."},
{name:"Klarer Rhythmus",style:"balance",category:"focus",subtle:true,officeSafe:true,science:"coherent",text:"Eine strukturierte Atemübung für mehr mentale Ordnung.",reason:"Gut, wenn du dich sammeln willst, ohne müde zu werden.",script:"Atme in einem gleichmäßigen Rhythmus und lass den Atem weich bleiben."},
{name:"Finger Tracing",style:"finger",category:"grounding",subtle:true,officeSafe:true,science:"movement",text:"Atem plus kleine Bewegung als Aufmerksamkeitsanker.",reason:"Besonders hilfreich bei zerstreuter Aufmerksamkeit.",script:"Beim Hochstreichen einatmen, beim Runterstreichen ausatmen."},
{name:"Seated Reach Flow",style:"reach-soft",category:"movement",subtle:false,officeSafe:false,science:"movement",text:"Sanfte Bewegung, um Müdigkeit aus dem Oberkörper zu lösen.",reason:"Praktisch bei Erschöpfung durch langes Sitzen.",script:"Beim Einatmen Arme sanft anheben, beim Ausatmen wieder sinken lassen."}
],
energy:[
{name:"Reach & breathe",style:"reach",category:"energy",subtle:false,officeSafe:false,science:"movement",text:"Eine aktivierende Übung mit Armbewegung und Rhythmus.",reason:"Gut, wenn du körperlich etwas wacher werden möchtest.",script:"Atme ein, während du die Arme hebst. Atme aus, während du sie wieder senkst."},
{name:"Standing power breath",style:"power",category:"energy",subtle:false,officeSafe:false,science:"movement",text:"Öffnet den Oberkörper und bringt Wachheit ins System.",reason:"Hilfreich bei Trägheit oder einem Energietief.",script:"Atme ein und öffne den Brustkorb. Beim Ausatmen löst du die Spannung wieder."},
{name:"Aktivierende Nasenatmung",style:"energy",category:"energy",subtle:true,officeSafe:true,science:"coherent",text:"Eine kontrollierte, etwas präsentere Nasenatmung für neue Wachheit.",reason:"Gut, wenn du einen kurzen Energieimpuls suchst, ohne zu auffällig zu werden.",script:"Atme etwas aktiver, aber weiter ruhig durch die Nase. Bleibe aufrecht."},
{name:"Mini March Breath",style:"march",category:"movement",subtle:false,officeSafe:false,science:"movement",text:"Kleine Marschbewegung plus Atemrhythmus.",reason:"Gut als kurzer Aktivierungs-Reset zwischendurch.",script:"Marsch leicht auf der Stelle. Einatmen über zwei Schritte, ausatmen über zwei bis drei Schritte."},
{name:"Calm energy",style:"balance",category:"focus",subtle:true,officeSafe:true,science:"coherent",text:"Mehr Klarheit ohne Überstimulation.",reason:"Praktisch, wenn du Energie und Ruhe zugleich brauchst.",script:"Atme gleichmäßig und etwas präsenter, aber nicht hektisch."}
],
presentation:[
{name:"Presentation reset",style:"calm",category:"calm",subtle:true,officeSafe:true,science:"slowExhale",text:"Hilft, Nervosität zu senken, ohne dich schläfrig zu machen.",reason:"Vor Auftritten ist ruhige Regulierung oft hilfreicher als sehr tiefe Entspannung.",script:"Atme ruhig ein und länger aus. Lass Kiefer, Bauch und Schultern weich werden."},
{name:"Steady presence",style:"coherent",category:"focus",subtle:true,officeSafe:true,science:"coherent",text:"Ein klarer Rhythmus für Ruhe und Präsenz.",reason:"Gut vor dem Sprechen, wenn du geerdet und wach sein willst.",script:"Atme gleichmäßig ein und aus und richte dich innerlich auf."},
{name:"Physiologischer Seufzer",style:"sigh",category:"calm",subtle:false,officeSafe:false,science:"physioSigh",text:"Kann eine akute Nervositätsspitze rasch entschärfen.",reason:"Eher für den Moment kurz vor dem Auftritt als für längere Praxis.",script:"Ein doppelter Einatemzug, dann eine lange weiche Ausatmung. Wenige Wiederholungen."}
],
call:[
{name:"Call reset",style:"calm-short",category:"reset",subtle:true,officeSafe:true,science:"slowExhale",text:"Eine kleine Zwischen-Übung, um sauber in den nächsten Call zu wechseln.",reason:"Ideal bei engem Takt zwischen Gesprächen.",script:"Atme drei bis fünf Mal ruhig ein und etwas länger aus."},
{name:"Walking breath",style:"walking",category:"movement",subtle:false,officeSafe:false,science:"movement",text:"Bewegung und Atemrhythmus für Übergänge.",reason:"Hilfreich, wenn du kurz aufstehen und den Kopf frei bekommen kannst.",script:"Gehe ruhig und atme über wenige Schritte ein und etwas länger aus."},
{name:"Atem beobachten",style:"observe",category:"awareness",subtle:true,officeSafe:true,science:"observe",text:"Für einen stillen Reset ohne zusätzliche Steuerung.",reason:"Gut nach vielen Reizen oder Informationsdichte.",script:"Beobachte den Atem für einen Moment und lass ihn von selbst kommen und gehen."}
],
overload:[
{name:"Atem beobachten",style:"observe",category:"awareness",subtle:true,officeSafe:true,science:"observe",text:"Weniger tun, mehr wahrnehmen – gut bei mentaler Überlastung.",reason:"Wenn ohnehin schon zu viel los ist, hilft oft eine einfache, nicht-komplexe Übung am meisten.",script:"Beobachte deinen Atem 30 bis 60 Sekunden lang."},
{name:"Finger Tracing",style:"finger",category:"grounding",subtle:true,officeSafe:true,science:"movement",text:"Berührung, Rhythmus und Atem bündeln die Aufmerksamkeit.",reason:"Gut, wenn dein Kopf zu viele offene Tabs hat.",script:"Streiche langsam Finger für Finger entlang und verbinde es mit Ein- und Ausatmung."},
{name:"3 ruhige Atemzüge",style:"calm-short",category:"reset",subtle:true,officeSafe:true,science:"slowExhale",text:"Ein kleiner Anker ohne viel Aufwand.",reason:"Gut, wenn du dich schnell wieder sortieren willst.",script:"Drei ruhige Atemzüge, mit etwas längerer Ausatmung."},
{name:"Shake & breathe",style:"shake",category:"movement",subtle:false,officeSafe:false,science:"movement",text:"Wenn Überlastung körperlich spürbar ist, kann Bewegung zuerst sinnvoll sein.",reason:"Hilfreich bei innerer Unruhe, die sich im Körper staut.",script:"Locker ausschütteln, dann stehenbleiben und den Atem wieder wahrnehmen."}
],
sleep:[
{name:"Sleep exhale",style:"sleep",category:"sleep",subtle:true,officeSafe:true,allowPause:true,science:"slowExhale",text:"Eine weiche Abendübung mit längerer Ausatmung.",reason:"Für Schlaf ist ein sanfter, verlangsamter Rhythmus meist passender als zu viel Technik.",script:"Ruhig einatmen und deutlich länger ausatmen. Nur wenn es angenehm ist, darf nach der Ausatmung ein kleiner natürlicher Moment Stille entstehen."},
{name:"4-6 Abendatmung",style:"sleep-soft",category:"sleep",subtle:true,officeSafe:true,allowPause:false,science:"slowExhale",text:"Eine mildere Abendvariante ohne lange Atemhaltephasen.",reason:"Besser geeignet für sensible oder unruhige Tage als strengere Schlafmuster.",script:"Atme weich durch die Nase ein und länger aus. Kein Zwang, keine Leistung."},
{name:"Soft breath awareness",style:"observe",category:"sleep",subtle:true,officeSafe:true,science:"observe",text:"Wenn du abends nichts mehr steuern möchtest.",reason:"Entlastend, wenn aktive Atemtechnik eher Druck erzeugt.",script:"Lege eine Hand auf Brust oder Bauch und beobachte deinen Atem, ohne ihn zu verändern."}
],
thoughts:[
{name:"Raum durch Ausatmung",style:"thoughts",category:"calm",subtle:true,officeSafe:true,allowPause:true,science:"slowExhale",text:"Hilft, Gedankendruck zu verringern und etwas mehr inneren Raum zu spüren.",reason:"Längere Ausatmung kann bei Grübeln oft einfacher wirken als komplexe Muster.",script:"Atme ruhig ein und länger aus. Stell dir vor, mit jeder Ausatmung wird es innen etwas weiter."},
{name:"Atem zählen",style:"counting",category:"focus",subtle:true,officeSafe:true,science:"observe",text:"Gibt dem Geist eine kleine, klare Aufgabe.",reason:"Hilfreich bei kreisenden Gedanken.",script:"Zähle die Ausatmungen von 1 bis 10 und beginne dann wieder bei 1."},
{name:"Finger Tracing",style:"finger",category:"grounding",subtle:true,officeSafe:true,science:"movement",text:"Körperlicher Anker für einen überaktiven Kopf.",reason:"Die kleine Bewegung hilft, Aufmerksamkeit zu bündeln.",script:"Finger für Finger hoch und runter streichen, passend zu Ein- und Ausatmung."},
{name:"Walking breath",style:"walking",category:"movement",subtle:false,officeSafe:false,science:"movement",text:"Gedanken in Bewegung bringen statt nur sitzen und denken.",reason:"Hilfreich, wenn Stillsein das Grübeln eher verstärkt.",script:"Gehe langsam, atme über wenige Schritte ein und etwas länger aus."}
]
};

function getValue(name){
const checked=document.querySelector(`input[name="${name}"]:checked`);
return checked?checked.value:null;
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
if(style==="reach" || style==="power" || style==="reach-soft"){inhale=3;exhale=3;}
if(style==="march"){inhale=2;exhale=3;}
if(style==="sleep"){inhale=4;exhale=6;}
if(style==="sleep-soft"){inhale=4;exhale=6;}
if(style==="thoughts"){inhale=4;exhale=6;}
if(style==="counting"){inhale=4;exhale=5;}
if(style==="walking"){inhale=3;exhale=4;}
if(style==="finger"){inhale=4;exhale=4;}
if(style==="shake"){inhale=2;exhale=2;}
if(style==="shoulder-roll"){inhale=4;exhale=5;}
if(style==="stand-reset"){inhale=3;exhale=4;}
if(style==="hum"){inhale=4;exhale=6;}

if(cp==="low"){
inhale=Math.max(2, inhale-1);
exhale=Math.max(inhale, exhale-1);
pause=0;
if(["sleep","thoughts","deep-calm","hum"].includes(style)){
exhale=Math.max(inhale+1, exhale-1);
}
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
if(style==="reach" || style==="reach-soft") return {inLabel:"Arme heben",outLabel:"Arme senken",inShort:"Hoch",outShort:"Tief"};
if(style==="power") return {inLabel:"Brustraum öffnen",outLabel:"Lösen",inShort:"Öffnen",outShort:"Lösen"};
if(style==="walking") return {inLabel:"Gehen + ein",outLabel:"Gehen + aus",inShort:"Schritte ein",outShort:"Schritte aus"};
if(style==="finger") return {inLabel:"Hochstreichen",outLabel:"Runterstreichen",inShort:"Hoch",outShort:"Runter"};
if(style==="shake") return {inLabel:"Locker bewegen",outLabel:"Natürlich atmen",inShort:"Bewegen",outShort:"Atmen"};
if(style==="shoulder-roll") return {inLabel:"Schultern kreisen",outLabel:"Sinken lassen",inShort:"Kreisen",outShort:"Sinken"};
if(style==="march") return {inLabel:"Mini-Marsch",outLabel:"Weiter fließen",inShort:"Marsch",outShort:"Fluss"};
if(style==="stand-reset") return {inLabel:"Aufrichten",outLabel:"Loslassen",inShort:"Auf",outShort:"Los"};
if(style==="hum") return {inLabel:"Einatmen",outLabel:"Summen",inShort:"Ein",outShort:"Summ"};
return {inLabel:"Einatmen",outLabel:"Ausatmen",inShort:"Ein",outShort:"Aus"};
}

function personalizeTechnique(tech){
const cp=getValue("cp")||"mid";
const safety=getValue("safety")||"ok";
const subtle=getValue("subtle")||"no";
const t=timingFor(tech.style,cp,safety,tech.allowPause);
const science=scienceMap[tech.science] || "";
let office="";
if(subtle==="yes"){
office=tech.officeSafe
? "Diese Variante ist leise und im Büro in der Regel gut unauffällig umsetzbar."
: "Diese Variante ist eher nicht office-tauglich, weil Bewegung, Summen, Seufzen oder hörbare Ausatmung auffallen können.";
}

if(tech.style==="observe"){
return {
...tech,
pattern:"Natürliche Atmung",
sequence:[{label:"Beobachten",short:"Ruhe",seconds:4,scale:1}],
script:tech.script+" Du musst nichts anhalten oder korrigieren.",
science,
office
};
}

if(tech.style==="sigh"){
const exhale=cp==="low"?4:cp==="high"?7:6;
return {
...tech,
pattern:`2 Einatemzüge · ${exhale} Sek. aus`,
sequence:[
{label:"Einatmen",short:"Ein",seconds:2,scale:1.04},
{label:"Kleiner zweiter Einatemzug",short:"+Ein",seconds:1,scale:1.12},
{label:"Lange Ausatmung",short:"Aus",seconds:exhale,scale:.92}
],
script:tech.script+" Wenn dein Atemreiz früh kommt, halte die Ausatmung kürzer und ganz weich.",
science,
office
};
}

const labels=movementLabelFor(tech.style);
let sequence=[
{label:labels.inLabel,short:labels.inShort,seconds:t.inhale,scale:1.08},
{label:labels.outLabel,short:labels.outShort,seconds:t.exhale,scale:.94}
];
if(t.pause>0){
sequence.push({label:"Kurze Pause",short:"Pause",seconds:t.pause,scale:.92});
}

let pattern=`${t.inhale} Sek. ein · ${t.exhale} Sek. aus`;
if(tech.style==="walking") pattern=`${t.inhale} Schritte ein · ${t.exhale} Schritte aus`;
if(tech.style==="finger") pattern=`Hoch beim Einatmen · runter beim Ausatmen`;
if(tech.style==="shake") pattern=`Lockere Bewegung · natürlicher Atem`;
if(tech.style==="hum") pattern=`${t.inhale} Sek. ein · summend ${t.exhale} Sek. aus`;
if(t.pause>0) pattern+=` · ${t.pause} Sek. Pause`;

let extra="";
if(cp==="low") extra+=" Deine CO₂-Toleranz ist heute eher niedriger, deshalb bleibt der Rhythmus kürzer, weicher und ohne fordernde Pausen.";
if(cp==="mid") extra+=" Der Rhythmus ist als sanfte Standardvariante gewählt.";
if(cp==="high") extra+=" Deine CO₂-Toleranz erlaubt heute einen etwas längeren, ruhigeren Rhythmus.";
if(safety==="no") extra+=" Atempausen sind ausgeschlossen.";

if(tech.category==="energy" && cp==="low"){
extra+=" Bei wenig Atemruhe bleibt die Aktivierung bewusst moderat, damit sie nicht kippt.";
}
if(tech.category==="movement"){
extra+=" Die Bewegung unterstützt den Atem, sie soll kein Workout werden.";
}

return {
...tech,
pattern,
sequence,
script:tech.script+extra,
science,
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
filtered=filtered.filter(t=>!["pulse","deep-hold"].includes(t.style));
filtered=filtered.filter(t=>t.style!=="sigh" || (getValue("goal")==="presentation"));
}

if(safety==="no"){
filtered=filtered.filter(t=>t.allowPause!==true || ["observe","calm-short","calm","meeting-calm","coherent","balance","finger","walking","shoulder-roll","stand-reset","reach-soft","sleep-soft","thoughts","counting","energy","reach","power","hum"].includes(t.style));
filtered=filtered.map(t=>({...t,allowPause:false}));
}

if(cp==="low" && ["sleep","thoughts","stress"].includes(getValue("goal"))){
filtered=filtered.filter(t=>!["deep-calm","hum"].includes(t.style) || t.subtle);
}

if(filtered.length===0){
filtered=[...list].filter(t=>t.subtle===true);
}
if(filtered.length===0){
filtered=[techniques.reset[0],techniques.reset[3]];
}
return filtered;
}

function sortByGoalLogic(goal,list){
const priorities={
stress:["calm","deep-calm","hum","calm-short","observe","sigh"],
sleep:["sleep-soft","sleep","observe"],
focus:["coherent","balance","finger","reach-soft"],
"meeting-start":["meeting-calm","coherent","finger"],
energy:["energy","balance","reach","power","march"],
overload:["observe","finger","calm-short","walking","shake"],
thoughts:["thoughts","counting","finger","walking"],
reset:["calm-short","observe","walking","shoulder-roll","shake"],
call:["calm-short","observe","walking"],
"meeting-end":["calm","calm-short","stand-reset"],
presentation:["coherent","calm","sigh"]
};
const priority=priorities[goal]||[];
return list.sort((a,b)=>{
const ai=priority.indexOf(a.style);
const bi=priority.indexOf(b.style);
return (ai===-1?99:ai)-(bi===-1?99:bi);
});
}

function pickTechniques(){
const goal=getValue("goal");
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
scienceText.textContent=tech.science;
factText.textContent=facts[Math.floor(Math.random()*facts.length)];
officeNote.textContent=tech.office || "";
resultEl.classList.add("show");
startBreathingAnimation(tech.sequence, tech.style);
}

function clearBreathTimers(){
breathTimeouts.forEach(t=>clearTimeout(t));
breathTimeouts.forEach(t=>clearInterval(t));
breathTimeouts=[];
}

function poseForPhase(phaseLabel, style){
const isOut=/aus|summ|lösen|sinken|runter/i.test(phaseLabel);
const isPause=/pause|ruhe|beobachten/i.test(phaseLabel);
if(isPause){
breathPerson.style.transform="scale(0.98)";
breathGlow.style.transform="scale(0.9)";
return;
}
if(isOut){
breathPerson.style.transform="scale(0.97) translateY(4px)";
breathGlow.style.transform="scale(0.88)";
}else{
breathPerson.style.transform="scale(1.03) translateY(-2px)";
breathGlow.style.transform="scale(1.12)";
}
}

function runPhase(sequence,index,style){
const phase=sequence[index];
phaseText.textContent=phase.label;
poseForPhase(phase.label, style);

let remaining=phase.seconds;
const updateLabel=()=>{ phaseText.textContent=`${phase.label} · ${remaining}`; };
updateLabel();

const countdown=setInterval(()=>{
remaining--;
if(remaining>=0) updateLabel();
},1000);
breathTimeouts.push(countdown);

const next=setTimeout(()=>{
clearInterval(countdown);
runPhase(sequence,(index+1)%sequence.length,style);
},phase.seconds*1000);
breathTimeouts.push(next);
}

function startBreathingAnimation(sequence,style){
clearBreathTimers();
breathPerson.style.transition="transform 1s linear";
breathGlow.style.transition="transform 1s linear";
breathPerson.style.transform="scale(1)";
breathGlow.style.transform="scale(1)";
phaseText.textContent="Gleich geht’s los";
const starter=setTimeout(()=>runPhase(sequence,0,style),250);
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
</script>
</body>
</html>
