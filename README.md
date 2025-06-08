# Ib
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>IB Psychology SAR Study</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f5f6fa;
      color: #2c3e50;
      margin: 0;
      padding: 20px;
      transition: background-color 0.3s, color 0.3s;
    }
    header {
      background-color: #273c75;
      color: white;
      padding: 20px;
      text-align: center;
    }
    nav {
      text-align: center;
      margin: 15px 0;
    }
    nav a {
      margin: 0 10px;
      text-decoration: none;
      color: #2980b9;
      font-weight: bold;
    }
    section {
      background: white;
      padding: 20px;
      margin: 20px auto;
      max-width: 850px;
      border-radius: 8px;
      box-shadow: 0 0 8px rgba(0,0,0,0.1);
    }
    h2 {
      color: #192a56;
    }
    .highlight {
      background-color: #dcdde1;
      padding: 10px;
      border-left: 5px solid #44bd32;
      margin: 10px 0;
    }
    textarea {
      width: 100%;
      height: 100px;
      margin-top: 10px;
      border-radius: 4px;
      border: 1px solid #ccc;
      padding: 10px;
      font-size: 14px;
      resize: vertical;
    }
    .flashcards button, .quiz button, .toggle-btn {
      margin-top: 10px;
      padding: 8px 15px;
      border: none;
      border-radius: 4px;
      background-color: #2980b9;
      color: white;
      cursor: pointer;
    }
    .toggle-btn {
      float: right;
      margin-top: -60px;
      margin-right: 20px;
    }
    .flashcard {
      background-color: #ecf0f1;
      border: 1px solid #bdc3c7;
      border-radius: 8px;
      padding: 15px;
      margin: 10px 0;
    }
    .dark-mode {
      background-color: #1e272e;
      color: #dcdde1;
    }
    .dark-mode header {
      background-color: #0c2461;
    }
    .dark-mode section {
      background-color: #2f3640;
    }
    .dark-mode .highlight {
      background-color: #353b48;
      color: #dcdde1;
    }
    .dark-mode nav a {
      color: #74b9ff;
    }
  </style>
</head>
<body>

  <header>
    <h1>IB Psychology SAR Study</h1>
    <button class="toggle-btn" onclick="toggleDarkMode()">Toggle Dark Mode</button>
  </header>

  <nav>
    <a href="#bio">Biological</a>
    <a href="#cog">Cognitive</a>
    <a href="#soc">Sociocultural</a>
    <a href="#tools">Study Tools</a>
  </nav>

  <section id="bio">
    <h2>Biological Approach SAR</h2>
    <p><strong>Question:</strong> Using one or more examples, explain localization of function.</p>
    <div class="highlight">Localization of function = specific brain areas control specific behaviors.</div>
    <p><strong>Study:</strong> Feinstein et al. (2011): Woman “SM” with damaged amygdalas didn’t react to fear stimuli.</p>
    <p><strong>Conclusion:</strong> Supports the amygdala’s role in fear responses.</p>
    <label><strong>Your Practice Response:</strong></label>
    <textarea placeholder="Type your biological SAR answer here..."></textarea>
  </section>

  <section id="cog">
    <h2>Cognitive Approach SAR</h2>
    <p><strong>Question:</strong> Describe how one study demonstrates reconstructive memory.</p>
    <div class="highlight">Reconstructive memory = memories are altered by later information.</div>
    <p><strong>Study:</strong> Loftus and Palmer (1974): Car crash videos + verbs like “hit” vs. “smashed” affected memory recall.</p>
    <p><strong>Conclusion:</strong> Shows memory can be influenced by wording.</p>
    <label><strong>Your Practice Response:</strong></label>
    <textarea placeholder="Type your cognitive SAR answer here..."></textarea>
  </section>

  <section id="soc">
    <h2>Sociocultural Approach SAR</h2>
    <p><strong>Question:</strong> Describe the social identity theory.</p>
    <div class="highlight">Social identity theory = we define ourselves through group membership.</div>
    <p><strong>Study:</strong> Tajfel et al. (1970): Boys favored their own group even with meaningless criteria.</p>
    <p><strong>Conclusion:</strong> Group membership influences behavior, even when arbitrary.</p>
    <label><strong>Your Practice Response:</strong></label>
    <textarea placeholder="Type your sociocultural SAR answer here..."></textarea>
  </section>

  <section id="tools">
    <h2>Flashcards</h2>
    <div class="flashcard" id="flashcard">Click to reveal answer</div>
    <button onclick="nextCard()">Next Flashcard</button>

    <h2 style="margin-top: 40px;">Practice Quiz</h2>
    <div class="quiz">
      <p><strong>Which brain region is associated with fear processing?</strong></p>
      <button onclick="checkAnswer(this, true)">Amygdala ✅</button>
      <button onclick="checkAnswer(this, false)">Hippocampus</button>
      <button onclick="checkAnswer(this, false)">Cerebellum</button>

      <p><strong>What did Loftus & Palmer’s study show about memory?</strong></p>
      <button onclick="checkAnswer(this, true)">Memory can be distorted by wording ✅</button>
      <button onclick="checkAnswer(this, false)">Memory is 100% reliable</button>

      <p><strong>What does Social Identity Theory say?</strong></p>
      <button onclick="checkAnswer(this, true)">Group identity influences behavior ✅</button>
      <button onclick="checkAnswer(this, false)">People act alone more often</button>
    </div>
  </section>

  <script>
    function toggleDarkMode() {
      document.body.classList.toggle("dark-mode");
    }

    // Flashcard system
    const flashcards = [
      { q: "What does the amygdala do?", a: "Processes fear. Damage can remove fear response (Feinstein et al.)" },
      { q: "What does Loftus & Palmer’s study show?", a: "Memory is reconstructive and can be altered by wording." },
      { q: "What is Social Identity Theory?", a: "We define ourselves by group identity, which leads to favoritism." }
    ];
    let currentCard = 0;
    const flashcardDiv = document.getElementById("flashcard");

    flashcardDiv.addEventListener("click", () => {
      const card = flashcards[currentCard];
      flashcardDiv.textContent = flashcardDiv.textContent === card.q ? card.a : card.q;
    });

    function nextCard() {
      currentCard = (currentCard + 1) % flashcards.length;
      flashcardDiv.textContent = flashcards[currentCard].q;
    }

    nextCard(); // initialize with the first card

    // Quiz system
    function checkAnswer(button, correct) {
      if (correct) {
        button.style.backgroundColor = "#27ae60";
        button.textContent += " ✔️";
      } else {
        button.style.backgroundColor = "#c0392b";
        button.textContent += " ❌";
      }
      button.disabled = true;
    }
  </script>

</body>
</html>
