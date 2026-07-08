<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Finde deine Lebensluft</title>
  <style>
    :root{
      --bg: #f6f5f0;
      --card: #ffffff;
      --text: #18352b;
      --muted: #5f746a;
      --line: #dbe4de;
      --green: #1f4d3c;
      --green-soft: #dfe9e4;
      --green-light: #edf3ef;
      --accent: #2d6a52;
      --shadow: 0 10px 30px rgba(24,53,43,0.08);
      --radius: 18px;
      --max: 980px;
    }

    * { box-sizing: border-box; }

    body{
      margin:0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.55;
    }

    .wrap{
      max-width: var(--max);
      margin: 0 auto;
      padding: 32px 20px 80px;
    }

    .hero{
      padding: 36px 0 18px;
    }

    .eyebrow{
      color: var(--accent);
      font-size: 0.95rem;
      letter-spacing: 0.02em;
      margin-bottom: 10px;
    }

    h1{
      font-size: clamp(2rem, 5vw, 3.2rem);
      line-height: 1.08;
      margin: 0 0 14px;
      font-weight: 600;
      color: var(--green);
    }

    .intro{
      font-size: 1.08rem;
      max-width: 760px;
      color: var(--muted);
      margin: 0 0 12px;
    }

    .disclaimer{
      font-size: 0.83rem;
      color: var(--muted);
      margin-top: 14px;
    }

    .card{
      background: var(--card);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 24px;
      margin-top: 22px;
    }

    h2{
      font-size: 1.35rem;
      margin: 0 0 14px;
      color: var(--green);
      font-weight: 600;
    }

    .question{
      margin-bottom: 22px;
    }

    .question-title{
      font-size: 1rem;
      font-weight: 600;
      margin-bottom: 10px;
      color: var(--text);
    }

    .option-grid{
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 10px;
    }

    .option-grid.three{
      grid-template-columns: repeat(3, minmax(0, 1fr));
    }

    .option-grid.four{
      grid-template-columns: repeat(4, minmax(0, 1fr));
    }

    .option-grid.goal-grid{
      grid-template-columns: repeat(3, minmax(0, 1fr));
    }

    .option{
      position: relative;
    }

    .option input{
      position: absolute;
      opacity: 0;
      pointer-events: none;
    }

    .option label{
      display: block;
      border: 1px solid var(--line);
      background: #fff;
      color: var(--text);
      padding: 14px 14px;
      border-radius: 14px;
      cursor: pointer;
      transition: all 0.2s ease;
      min-height: 54px;
    }

    .option label:hover{
      border-color: #bfd0c6;
      background: var(--green-light);
    }

    .option input:checked + label{
      background: var(--green-soft);
      border-color: var(--accent);
      color: var(--green);
      box-shadow: inset 0 0 0 1px var(--accent);
    }

    details{
      border: 1px solid var(--line);
      border-radius: 14px;
      background: #fcfcfa;
      padding: 0;
      overflow: hidden;
    }

    summary{
      list-style: none;
      cursor: pointer;
      padding: 16px 18px;
      font-weight: 600;
      color: var(--green);
      background: #fafaf7;
    }

    summary::-webkit-details-marker{ display:none; }

    .details-inner{
      padding: 6px 18px 18px;
      border-top: 1px solid var(--line);
    }

    .help{
      font-size: 0.92rem;
      color: var(--muted);
      margin: 6px 0 12px;
    }

    .inline-note{
      font-size: 0.9rem;
      color: var(--muted);
      margin-top: 8px;
    }

    .actions{
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
      margin-top: 10px;
    }

    button{
      appearance: none;
      border: none;
      border-radius: 999px;
      padding: 14px 22px;
      font-size: 1rem;
      cursor: pointer;
      transition: transform 0.15s ease, opacity 0.2s ease, background 0.2s ease;
    }

    button:hover{
      transform: translateY(-1px);
    }

    .btn-primary{
      background: var(--green);
      color: #fff;
    }

    .btn-secondary{
      background: var(--green-light);
      color: var(--green);
      border: 1px solid var(--line);
    }

    .result{
      display: none;
      margin-top: 24px;
      border-top: 1px solid var(--line);
      padding-top: 24px;
    }

    .result.show{
      display: block;
    }

    .result-box{
      background: linear-gradient(180deg, #fcfdfb 0%, #f3f7f4 100%);
      border: 1px solid var(--line);
      border-radius: 18px;
      padding: 22px;
    }

    .result-kicker{
      color: var(--accent);
      font-size: 0.92rem;
      margin-bottom: 6px;
    }

    .result-title{
      font-size: 1.45rem;
      color: var(--green);
      margin: 0 0 10px;
      font-weight: 600;
    }

    .result-text{
      margin: 0 0 14px;
      color: var(--text);
    }

    .result-reason{
      color: var(--muted);
      font-size: 0.97rem;
      margin-bottom: 18px;
    }

    .breath-visual{
      margin-top: 12px;
      padding: 20px 12px 12px;
      background: #fff;
      border: 1px solid var(--line);
      border-radius: 18px;
      text-align: center;
    }

    .circle-wrap{
      display:flex;
      justify-content:center;
      align-items:center;
      min-height: 250px;
    }

    .circle{
      width: 154px;
      height: 154px;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 30%, #d9e8e0, #87ad99 58%, #2d6a52 100%);
      display:flex;
      align-items:center;
      justify-content:center;
      color:#fff;
      text-align:center;
      font-weight:600;
      padding: 14px;
      box-shadow: 0 18px 40px rgba(31,77,60,0.18);
      transform: scale(1);
      transition: transform 1s linear;
      will-change: transform;
    }

    .circle span{
      display:block;
      font-size: 1rem;
      line-height: 1.35;
    }

    .phase{
      margin-top: 8px;
      font-size: 0.95rem;
      color: var(--muted);
      min-height: 24px;
    }

    .pattern{
      margin-top: 10px;
      color: var(--green);
      font-weight: 600;
    }

    .script{
      margin-top: 16px;
      padding: 14px 16px;
      border-radius: 14px;
      background: var(--green-light);
      color: var(--text);
      font-size: 0.96rem;
    }

    .footer-note{
      margin-top: 14px;
      color: var(--muted);
      font-size: 0.88rem;
    }

    @media (max-width: 860px){
      .option-grid,
      .option-grid.three,
      .option-grid.four,
      .option-grid.goal-grid{
        grid-template-columns: 1fr;
      }

      .card{
        padding: 18px;
      }

      .circle{
        width: 136px;
        height: 136px;
      }
    }
  </style>
</head>
<body>
  <div class="wrap">
    <section class="hero">
      <div class="eyebrow">Finde deine Lebensluft</div>
      <h1>Atemübungen für den Alltag</h1>
      <p class="intro">
        Finde in wenigen Schritten eine Atemübung, die zu deinem Moment passt — ruhig, klar und direkt anwendbar.
        Für Stress, Fokus, Meetings, Pausen oder neue Energie.
      </p>
      <p class="disclaimer">
        Hinweis: Dieses Tool ersetzt keine medizinische Abklärung. Bei starker Atemnot, Brustschmerz oder Schwindel nutze bitte keine Atempausen.
      </p>
    </section>

    <section class="card">
      <h2>Passende Übung finden</h2>

      <div class="question">
        <div class="question-title">Was brauchst du gerade?</div>
        <div class="option-grid goal-grid">
          <div class="option">
            <input type="radio" id="goal-stress" name="goal" value="stress" checked>
            <label for="goal-stress">Stress runterfahren</label>
          </div>
          <div class="option">
            <input type="radio" id="goal-reset" name="goal" value="reset">
            <label for="goal-reset">Resetten</label>
          </div>
          <div class="option">
            <input type="radio" id="goal-meeting-start" name="goal" value="meeting-start">
            <label for="goal-meeting-start">Meeting starten</label>
          </div>
          <div class="option">
            <input type="radio" id="goal-meeting-end" name="goal" value="meeting-end">
            <label for="goal-meeting-end">Meeting beenden</label>
          </div>
          <div class="option">
            <input type="radio" id="goal-focus" name="goal" value="focus">
            <label for="goal-focus">Fokus finden</label>
          </div>
          <div class="option">
            <input type="radio" id="goal-energy" name="goal" value="energy">
            <label for="goal-energy">Energie bekommen</label>
          </div>
          <div class="option">
            <input type="radio" id="goal-presentation" name="goal" value="presentation">
            <label for="goal-presentation">Vor Präsentation</label>
          </div>
          <div class="option">
            <input type="radio" id="goal-call" name="goal" value="call">
            <label for="goal-call">Zwischen zwei Calls</label>
          </div>
          <div class="option">
            <input type="radio" id="goal-overload" name="goal" value="overload">
            <label for="goal-overload">Mentale Überladung</label>
          </div>
        </div>
      </div>

      <div class="question">
        <div class="question-title">Wie viel Zeit hast du?</div>
        <div class="option-grid four">
          <div class="option">
            <input type="radio" id="time-30" name="time" value="30" checked>
            <label for="time-30">30 Sek.</label>
          </div>
          <div class="option">
            <input type="radio" id="time-60" name="time" value="60">
            <label for="time-60">1 Min.</label>
          </div>
          <div class="option">
            <input type="radio" id="time-120" name="time" value="120">
            <label for="time-120">2 Min.</label>
          </div>
          <div class="option">
            <input type="radio" id="time-300" name="time" value="300">
            <label for="time-300">3–5 Min.</label>
          </div>
        </div>
      </div>

      <div class="question">
        <div class="question-title">Soll es unauffällig sein?</div>
        <div class="option-grid">
          <div class="option">
            <input type="radio" id="subtle-yes" name="subtle" value="yes" checked>
            <label for="subtle-yes">Ja, büro-freundlich</label>
          </div>
          <div class="option">
            <input type="radio" id="subtle-no" name="subtle" value="no">
            <label for="subtle-no">Nein, ist egal</label>
          </div>
        </div>
      </div>

      <div class="question">
        <div class="question-title">Wie fühlst du dich gerade?</div>
        <div class="option-grid goal-grid">
          <div class="option">
            <input type="checkbox" id="state-tense" name="state" value="tense">
            <label for="state-tense">Angespannt</label>
          </div>
          <div class="option">
            <input type="checkbox" id="state-busy" name="state" value="busy">
            <label for="state-busy">Mental voll</label>
          </div>
          <div class="option">
            <input type="checkbox" id="state-flat" name="state" value="flat">
            <label for="state-flat">Müde</label>
          </div>
          <div class="option">
            <input type="checkbox" id="state-restless" name="state" value="restless">
            <label for="state-restless">Innerlich unruhig</label>
          </div>
          <div class="option">
            <input type="checkbox" id="state-pressure" name="state" value="pressure">
            <label for="state-pressure">Unter Druck</label>
          </div>
          <div class="option">
            <input type="checkbox" id="state-scattered" name="state" value="scattered">
            <label for="state-scattered">Unfokussiert</label>
          </div>
        </div>
      </div>

      <details id="individualizeBox">
        <summary>Individualisiere deine Übung</summary>
        <div class="details-inner">
          <p class="help">
            Optional: Ein kurzer Atem-Check hilft dabei, die Intensität besser anzupassen.
            Bei Meeting-Zielen wird dieser Schritt nicht benötigt.
          </p>

          <div class="question">
            <div class="question-title">Sicherheit</div>
            <div class="option-grid">
              <div class="option">
                <input type="radio" id="safe-ok" name="safety" value="ok" checked>
                <label for="safe-ok">Passt gerade</label>
              </div>
              <div class="option">
                <input type="radio" id="safe-no" name="safety" value="no">
                <label for="safe-no">Lieber ohne Atempause</label>
              </div>
            </div>
            <div class="inline-note">Bei Brustschmerz, starker Atemnot oder Schwindel bitte keinen Atemtest machen.</div>
          </div>

          <div class="question">
            <div class="question-title">Atem-Check</div>
            <p class="help">
              Atme normal ein und aus. Halte nach der Ausatmung kurz die Nase zu. Stoppe beim ersten klaren Atemimpuls.
            </p>
            <div class="option-grid three">
              <div class="option">
                <input type="radio" id="cp-low" name="cp" value="low" checked>
                <label for="cp-low">Unter 20 Sek.</label>
              </div>
              <div class="option">
                <input type="radio" id="cp-mid" name="cp" value="mid">
                <label for="cp-mid">20–30 Sek.</label>
              </div>
              <div class="option">
                <input type="radio" id="cp-high" name="cp" value="high">
                <label for="cp-high">Über 30 Sek.</label>
              </div>
            </div>
          </div>
        </div>
      </details>

      <div class="actions">
        <button class="btn-primary" id="findBtn">Passende Übung finden</button>
      </div>

      <div class="result" id="result">
        <div class="result-box">
          <div class="result-kicker">Deine Empfehlung</div>
          <h3 class="result-title" id="resultTitle">Verlängerte Ausatmung</h3>
          <p class="result-text" id="resultText"></p>
          <p class="result-reason" id="resultReason"></p>

          <div class="breath-visual">
            <div class="circle-wrap">
              <div class="circle" id="breathCircle">
                <span id="circleText">Bereit</span>
              </div>
            </div>
            <div class="phase" id="phaseText">Starte gleich</div>
            <div class="pattern" id="patternText">4 Sek. ein · 6 Sek. aus</div>
          </div>

          <div class="script" id="scriptText"></div>

          <div class="actions" style="margin-top:18px;">
            <button class="btn-secondary" id="altBtn">Alternative Übung anzeigen</button>
          </div>

          <div class="footer-note">
            Atme ruhig und ohne Druck. Wenn sich etwas unangenehm anfühlt, kehre zu deiner natürlichen Atmung zurück.
          </div>
        </div>
      </div>
    </section>
  </div>

  <script>
    const resultEl = document.getElementById("result");
    const resultTitle = document.getElementById("resultTitle");
    const resultText = document.getElementById("resultText");
    const resultReason = document.getElementById("resultReason");
    const patternText = document.getElementById("patternText");
    const scriptText = document.getElementById("scriptText");
    const phaseText = document.getElementById("phaseText");
    const circleText = document.getElementById("circleText");
    const breathCircle = document.getElementById("breathCircle");
    const findBtn = document.getElementById("findBtn");
    const altBtn = document.getElementById("altBtn");
    const individualizeBox = document.getElementById("individualizeBox");

    let currentPair = [];
    let currentTechnique = null;
    let breathTimeouts = [];

    const techniques = {
      "stress": [
        {
          name: "Verlängerte Ausatmung",
          pattern: "4 Sek. ein · 6 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 4, scale: 1.18 },
            { label: "Ausatmen", short: "Aus", seconds: 6, scale: 0.82 }
          ],
          text: "Folgende Übung könnte gut passen: Verlängerte Ausatmung. Sie hilft dir, Spannung zu senken und mehr Ruhe in deinen Atem zu bringen.",
          reason: "Sie passt gut bei Anspannung, Druck oder innerer Unruhe und bleibt gleichzeitig unauffällig.",
          script: "Atme 4 Sekunden ruhig durch die Nase ein. Atme 6 Sekunden weich aus. Wiederhole das für 1 bis 2 Minuten."
        },
        {
          name: "Physiologischer Seufzer",
          pattern: "2 Einatmungen · lange Ausatmung",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 2, scale: 1.00 },
            { label: "Noch einmal ein", short: "Ein", seconds: 1, scale: 1.18 },
            { label: "Lang ausatmen", short: "Aus", seconds: 6, scale: 0.80 }
          ],
          text: "Folgende Übung könnte gut passen: Physiologischer Seufzer. Sie kann helfen, einen akuten Spannungsmoment schneller zu lösen.",
          reason: "Gut bei Druck, Enge oder wenn du das Gefühl hast, einmal bewusst durchatmen zu müssen.",
          script: "Atme einmal ein. Nimm direkt einen kleinen zweiten Einatemzug oben drauf. Atme dann lang und weich aus. Wiederhole das 2 bis 4 Mal."
        }
      ],
      "reset": [
        {
          name: "3 ruhige Atemzüge",
          pattern: "4 Sek. ein · 5 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 4, scale: 1.15 },
            { label: "Ausatmen", short: "Aus", seconds: 5, scale: 0.84 }
          ],
          text: "Folgende Übung könnte gut passen: 3 ruhige Atemzüge. Sie hilft dir, kurz umzuschalten und wieder bei dir anzukommen.",
          reason: "Ideal zwischen Aufgaben, nach einem Call oder für einen bewussten Übergang.",
          script: "Atme 3 Mal ruhig durch die Nase ein und etwas länger aus. Lass mit jeder Ausatmung Schultern und Kiefer weicher werden."
        },
        {
          name: "Atembeobachtung",
          pattern: "Natürlich atmen",
          sequence: [
            { label: "Beobachten", short: "Ruhe", seconds: 4, scale: 1.00 }
          ],
          text: "Folgende Übung könnte gut passen: Atembeobachtung. Sie bringt Aufmerksamkeit zurück in den Körper, ohne dass du etwas leisten musst.",
          reason: "Besonders passend, wenn du mental voll bist oder erst einmal nichts aktiv steuern möchtest.",
          script: "Beobachte 30 bis 60 Sekunden lang nur deinen Atem. Spüre, wo er gerade ankommt, ohne ihn zu verändern."
        }
      ],
      "meeting-start": [
        {
          name: "Meeting-Ankommen",
          pattern: "4 Sek. ein · 6 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 4, scale: 1.15 },
            { label: "Ausatmen", short: "Aus", seconds: 6, scale: 0.84 }
          ],
          text: "Folgende Übung könnte gut passen: Meeting-Ankommen. Sie hilft dir, vor dem Start ruhiger, klarer und präsenter zu werden.",
          reason: "Für Meetings ist eine einfache, unauffällige Atemführung oft am hilfreichsten.",
          script: "Atme für 4 ruhige Atemrunden durch die Nase ein und etwas länger aus. Lass den Ausatem weich und unhörbar werden."
        },
        {
          name: "Box light",
          pattern: "4 Sek. ein · 4 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 4, scale: 1.12 },
            { label: "Ausatmen", short: "Aus", seconds: 4, scale: 0.88 }
          ],
          text: "Folgende Übung könnte gut passen: Box light. Sie schafft einen klaren Rhythmus und unterstützt einen ruhigen Einstieg.",
          reason: "Gut, wenn du Struktur magst und die Übung im Meeting dezent bleiben soll.",
          script: "Atme 4 Sekunden ein und 4 Sekunden aus. Halte den Rhythmus weich und gleichmäßig."
        }
      ],
      "meeting-end": [
        {
          name: "Ruhiger Ausklang",
          pattern: "4 Sek. ein · 6 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 4, scale: 1.14 },
            { label: "Ausatmen", short: "Aus", seconds: 6, scale: 0.84 }
          ],
          text: "Folgende Übung könnte gut passen: Ruhiger Ausklang. Sie hilft dir, nach einem Gespräch bewusst loszulassen und klar abzuschließen.",
          reason: "Passend am Ende eines Meetings oder vor dem Wechsel in die nächste Aufgabe.",
          script: "Nimm 3 bis 4 ruhige Atemzüge. Atme normal ein und etwas länger aus. Lass den letzten Ausatem besonders weich werden."
        },
        {
          name: "3 Ausatemzüge",
          pattern: "3 Sek. ein · 6 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 3, scale: 1.10 },
            { label: "Ausatmen", short: "Aus", seconds: 6, scale: 0.82 }
          ],
          text: "Folgende Übung könnte gut passen: 3 Ausatemzüge. Sie schafft schnell einen Abschluss und etwas mehr innere Ordnung.",
          reason: "Gut, wenn du direkt nach dem Meeting weiter musst und wenig Zeit hast.",
          script: "Atme 3 Mal ruhig ein und länger aus. Nutze den Ausatem, um das Gespräch bewusst abzuschließen."
        }
      ],
      "focus": [
        {
          name: "Kohärentes Atmen",
          pattern: "5 Sek. ein · 5 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 5, scale: 1.14 },
            { label: "Ausatmen", short: "Aus", seconds: 5, scale: 0.86 }
          ],
          text: "Folgende Übung könnte gut passen: Kohärentes Atmen. Sie unterstützt ruhige Wachheit und kann Fokus und Regulation verbinden.",
          reason: "Sinnvoll, wenn du dich sammeln und gleichzeitig ruhig bleiben möchtest.",
          script: "Atme 5 Sekunden ein und 5 Sekunden aus. Bleibe dabei entspannt und gleichmäßig."
        },
        {
          name: "Klare 4er-Atmung",
          pattern: "4 Sek. ein · 4 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 4, scale: 1.12 },
            { label: "Ausatmen", short: "Aus", seconds: 4, scale: 0.88 }
          ],
          text: "Folgende Übung könnte gut passen: Klare 4er-Atmung. Sie gibt deinem Atem eine einfache Struktur und hilft beim Sortieren.",
          reason: "Gut bei Unfokus oder wenn du nach einem klaren Rhythmus suchst.",
          script: "Atme 4 Sekunden ein und 4 Sekunden aus. Wiederhole das für 1 bis 3 Minuten."
        }
      ],
      "energy": [
        {
          name: "Aktivierende Nasenatmung",
          pattern: "3 Sek. ein · 3 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 3, scale: 1.12 },
            { label: "Ausatmen", short: "Aus", seconds: 3, scale: 0.90 }
          ],
          text: "Folgende Übung könnte gut passen: Aktivierende Nasenatmung. Sie kann dir helfen, wacher und präsenter zu werden.",
          reason: "Sinnvoll, wenn du eher müde oder flach bist und einen kurzen Energie-Impuls brauchst.",
          script: "Atme 30 bis 60 Sekunden etwas wacher, aber kontrolliert durch die Nase ein und aus. Bleib dabei aufrecht."
        },
        {
          name: "Kohärentes Atmen",
          pattern: "5 Sek. ein · 5 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 5, scale: 1.14 },
            { label: "Ausatmen", short: "Aus", seconds: 5, scale: 0.86 }
          ],
          text: "Folgende Übung könnte gut passen: Kohärentes Atmen. Es bringt ruhige Energie und kann dir helfen, wieder präsenter zu werden.",
          reason: "Gut, wenn du Energie suchst, ohne dich zusätzlich hochzufahren.",
          script: "Atme 5 Sekunden ein und 5 Sekunden aus. Bleib weich im Atem und gleichmäßig im Tempo."
        }
      ],
      "presentation": [
        {
          name: "Präsentations-Reset",
          pattern: "4 Sek. ein · 6 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 4, scale: 1.14 },
            { label: "Ausatmen", short: "Aus", seconds: 6, scale: 0.84 }
          ],
          text: "Folgende Übung könnte gut passen: Präsentations-Reset. Sie hilft dir, vor dem Sprechen ruhiger und klarer zu werden.",
          reason: "Gut vor Auftritten, wenn du Spannung senken möchtest, ohne an Wachheit zu verlieren.",
          script: "Atme 4 Sekunden ein und 6 Sekunden aus. Wiederhole das für 3 bis 5 Atemrunden, bevor du startest."
        },
        {
          name: "Box light",
          pattern: "4 Sek. ein · 4 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 4, scale: 1.12 },
            { label: "Ausatmen", short: "Aus", seconds: 4, scale: 0.88 }
          ],
          text: "Folgende Übung könnte gut passen: Box light. Sie gibt dir einen stabilen Rhythmus und unterstützt klare Präsenz.",
          reason: "Hilfreich, wenn du vor dem Sprechen gesammelt und strukturiert wirken möchtest.",
          script: "Atme 4 Sekunden ein und 4 Sekunden aus. Bleibe aufrecht und locker im Kiefer."
        }
      ],
      "call": [
        {
          name: "Call-Reset",
          pattern: "4 Sek. ein · 5 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 4, scale: 1.13 },
            { label: "Ausatmen", short: "Aus", seconds: 5, scale: 0.85 }
          ],
          text: "Folgende Übung könnte gut passen: Call-Reset. Sie hilft dir, kurz umzuschalten und wieder sauber in den nächsten Termin zu gehen.",
          reason: "Ideal zwischen zwei Gesprächen oder direkt nach einem intensiven Austausch.",
          script: "Nimm 3 bis 5 ruhige Atemzüge. Atme etwas länger aus als ein und lass den letzten Ausatem besonders weich werden."
        },
        {
          name: "Atembeobachtung",
          pattern: "Natürlich atmen",
          sequence: [
            { label: "Beobachten", short: "Ruhe", seconds: 4, scale: 1.00 }
          ],
          text: "Folgende Übung könnte gut passen: Atembeobachtung. Sie bringt dich kurz raus aus dem Reizfluss und zurück in einen klareren Kontakt mit dir.",
          reason: "Gut, wenn du nach vielen Reizen erst einmal nichts aktiv steuern möchtest.",
          script: "Beobachte deinen Atem für 30 bis 60 Sekunden. Nimm nur wahr, wie er gerade kommt und geht."
        }
      ],
      "overload": [
        {
          name: "Atembeobachtung",
          pattern: "Natürlich atmen",
          sequence: [
            { label: "Beobachten", short: "Ruhe", seconds: 4, scale: 1.00 }
          ],
          text: "Folgende Übung könnte gut passen: Atembeobachtung. Sie hilft dir, bei mentaler Überladung zuerst Druck rauszunehmen.",
          reason: "Passend, wenn gerade schon viel los ist und du nichts Komplexes mehr brauchst.",
          script: "Beobachte für 30 bis 60 Sekunden nur deinen Atem. Lass ihn so, wie er ist."
        },
        {
          name: "3 ruhige Atemzüge",
          pattern: "4 Sek. ein · 5 Sek. aus",
          sequence: [
            { label: "Einatmen", short: "Ein", seconds: 4, scale: 1.15 },
            { label: "Ausatmen", short: "Aus", seconds: 5, scale: 0.84 }
          ],
          text: "Folgende Übung könnte gut passen: 3 ruhige Atemzüge. Sie kann helfen, wieder einen kleinen inneren Anker zu finden.",
          reason: "Gut, wenn du dich sammeln möchtest, ohne dich zusätzlich anzustrengen.",
          script: "Atme 3 Mal ruhig ein und etwas länger aus. Halte den Atem weich und unaufgeregt."
        }
      ]
    };

    function getValue(name){
      const checked = document.querySelector(`input[name="${name}"]:checked`);
      return checked ? checked.value : null;
    }

    function getCheckedValues(name){
      return Array.from(document.querySelectorAll(`input[name="${name}"]:checked`)).map(el => el.value);
    }

    function isMeetingGoal(goal){
      return goal === "meeting-start" || goal === "meeting-end";
    }

    function pickTechniques(){
      const goal = getValue("goal");
      const subtle = getValue("subtle");
      const cp = getValue("cp");
      const safety = getValue("safety");
      const states = getCheckedValues("state");

      let list = [...(techniques[goal] || techniques["stress"])];

      if(states.includes("busy") || states.includes("scattered")){
        if(goal === "focus" || goal === "overload" || goal === "reset"){
          list = [list[0], techniques["overload"][0]];
        }
      }

      if(states.includes("restless") || states.includes("tense") || states.includes("pressure")){
        if(goal === "stress" || goal === "presentation"){
          list = [techniques["stress"][0], techniques["stress"][1]];
        }
      }

      if(states.includes("flat")){
        if(goal === "energy"){
          list = [techniques["energy"][0], techniques["energy"][1]];
        }
      }

      if(subtle === "yes"){
        list = list.filter(t => t.name !== "Physiologischer Seufzer");
        if(list.length < 2){
          if(goal === "stress") list.push(techniques["reset"][0]);
          if(goal === "energy") list.push(techniques["focus"][0]);
        }
      }

      if(!isMeetingGoal(goal)){
        if(safety === "no" || cp === "low"){
          if(goal === "energy"){
            list = [techniques["energy"][1], techniques["reset"][0]];
          } else if(goal === "stress" || goal === "presentation"){
            list = [techniques["stress"][0], techniques["reset"][1]];
          } else if(goal === "overload"){
            list = [techniques["overload"][0], techniques["reset"][0]];
          }
        }
      }

      const unique = [];
      const seen = new Set();
      for(const item of list){
        if(item && !seen.has(item.name)){
          unique.push(item);
          seen.add(item.name);
        }
      }
      return unique.slice(0, 2);
    }

    function renderTechnique(tech){
      currentTechnique = tech;
      resultTitle.textContent = tech.name;
      resultText.textContent = tech.text;
      resultReason.textContent = tech.reason;
      patternText.textContent = tech.pattern;
      scriptText.textContent = tech.script;
      resultEl.classList.add("show");
      startBreathingAnimation(tech.sequence);
    }

    function clearBreathTimers(){
      breathTimeouts.forEach(t => clearTimeout(t));
      breathTimeouts = [];
    }

    function runPhase(sequence, index){
      const phase = sequence[index];
      phaseText.textContent = phase.label;
      breathCircle.style.transition = `transform ${phase.seconds}s linear`;
      breathCircle.style.transform = `scale(${phase.scale})`;

      let remaining = phase.seconds;
      circleText.innerHTML = `${phase.short}<br>${remaining}`;

      const countdown = setInterval(() => {
        remaining--;
        if(remaining > 0){
          circleText.innerHTML = `${phase.short}<br>${remaining}`;
        } else {
          clearInterval(countdown);
          circleText.innerHTML = `${phase.short}<br>0`;
        }
      }, 1000);

      breathTimeouts.push(countdown);

      const next = setTimeout(() => {
        clearInterval(countdown);
        const nextIndex = (index + 1) % sequence.length;
        runPhase(sequence, nextIndex);
      }, phase.seconds * 1000);

      breathTimeouts.push(next);
    }

    function startBreathingAnimation(sequence){
      clearBreathTimers();
      breathCircle.style.transition = "none";
      breathCircle.style.transform = "scale(1)";
      circleText.innerHTML = "Bereit";
      phaseText.textContent = "Starte gleich";

      const starter = setTimeout(() => {
        runPhase(sequence, 0);
      }, 250);

      breathTimeouts.push(starter);
    }

    findBtn.addEventListener("click", () => {
      currentPair = pickTechniques();
      renderTechnique(currentPair[0]);
      resultEl.scrollIntoView({ behavior: "smooth", block: "start" });
    });

    altBtn.addEventListener("click", () => {
      if(currentPair.length > 1){
        currentPair.push(currentPair.shift());
        renderTechnique(currentPair[0]);
      }
    });

    document.querySelectorAll('input[name="goal"]').forEach(input => {
      input.addEventListener("change", (e) => {
        if(isMeetingGoal(e.target.value)){
          individualizeBox.open = false;
        }
      });
    });
  </script>
</body>
</html>
