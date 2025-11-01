<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bank Bridge | Empowering India's Underserved with Financial Knowledge</title>
  <meta name="description" content="Bank Bridge is a free, multilingual platform bringing financial literacy and inclusion to India's underserved communities." />
  <link rel="icon" href="https://upload.wikimedia.org/wikipedia/commons/7/7e/Rupee_symbol.svg" />

  <style>
    :root {
      --blue: #0052cc;
      --gold: #ffb703;
      --green: #06d6a0;
      --text: #202020;
      --bg: #f7f7f7;
      --radius: 10px;
      --shadow: 0 4px 12px rgba(0,0,0,0.1);
      --gradient: linear-gradient(135deg, #ffb703, #06d6a0);
      --font: "Poppins", "Segoe UI", sans-serif;
    }

    * {margin:0;padding:0;box-sizing:border-box;font-family:var(--font);scroll-behavior:smooth;}

    body {
      background: var(--bg);
      color: var(--text);
    }

    header {
      position: fixed;
      width: 100%;
      top: 0;
      left: 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 18px 8%;
      background: white;
      box-shadow: var(--shadow);
      z-index: 100;
    }

    header h1 {
      color: var(--blue);
      font-weight: 700;
      font-size: 1.6rem;
    }

    nav a {
      margin-left: 20px;
      text-decoration: none;
      color: var(--text);
      font-weight: 500;
      transition: 0.3s;
    }
    nav a:hover {color: var(--blue);}

    /* Hero */
    .hero {
      height: 100vh;
      padding: 0 8%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      background: var(--gradient);
      color: #fff;
    }

    .hero h2 {
      font-size: 2.8rem;
      max-width: 900px;
      line-height: 1.3;
      font-weight: 700;
    }

    .hero p {
      margin-top: 18px;
      max-width: 750px;
      font-size: 1.1rem;
      opacity: 0.95;
    }

    .cta {
      margin-top: 32px;
      background: white;
      color: var(--blue);
      border: none;
      padding: 14px 30px;
      border-radius: var(--radius);
      font-weight: 600;
      font-size: 1rem;
      box-shadow: var(--shadow);
      cursor: pointer;
      transition: 0.3s;
    }
    .cta:hover {transform: translateY(-2px);}

    /* Language selector */
    .lang-select {
      margin-top: 40px;
      padding: 12px 18px;
      border-radius: var(--radius);
      border: none;
      box-shadow: var(--shadow);
      font-weight: 500;
      color: var(--blue);
    }

    section {padding:100px 8%;}
    .section-title {
      text-align:center;
      font-size:2rem;
      color:var(--blue);
      font-weight:700;
      margin-bottom:40px;
    }

    footer {
      background: var(--blue);
      color: #fff;
      text-align: center;
      padding: 40px 8%;
      margin-top: 100px;
    }
  </style>
</head>

<body>
  <header>
    <h1>Bank Bridge</h1>
    <nav>
      <a href="#learn">Learn</a>
      <a href="#quiz">Quiz</a>
      <a href="#resources">Resources</a>
      <a href="#voice">Voice</a>
    </nav>
  </header>

  <section class="hero" id="home">
    <h2>Empowering India's Underserved with Financial Knowledge</h2>
    <p>Bank Bridge is a free, multilingual digital platform designed to bridge India's financial literacy gap — reaching families in every state with accessible lessons, local languages, and zero data barriers.</p>
    <button class="cta" onclick="document.getElementById('learn').scrollIntoView({behavior:'smooth'})">Start Learning</button>

    <select id="languageSelect" class="lang-select" onchange="changeLanguage(this.value)">
      <option value="en">English</option>
      <option value="hi">हिन्दी (Hindi)</option>
      <option value="bn">বাংলা (Bengali)</option>
      <option value="ta">தமிழ் (Tamil)</option>
      <option value="te">తెలుగు (Telugu)</option>
      <option value="ml">മലയാളം (Malayalam)</option>
      <option value="mr">मराठी (Marathi)</option>
      <option value="kn">ಕನ್ನಡ (Kannada)</option>
      <option value="gu">ગુજરાતી (Gujarati)</option>
      <option value="or">ଓଡ଼ିଆ (Odia)</option>
    </select>
  </section>

  <section id="learn">
    <h3 class="section-title">Learn Financial Basics</h3>
    <p style="text-align:center;max-width:700px;margin:auto;">Coming soon — short, animated, multilingual lessons that explain how to open a bank account, apply for welfare schemes, and use digital payments safely.</p>
  </section>

  <footer>
    <p>© 2025 Bank Bridge | Designed for Financial Inclusion in India</p>
  </footer>

  <script>
    async function changeLanguage(lang) {
      const textElements = document.querySelectorAll('h2, h3, p, button, a');
      for (let el of textElements) {
        const original = el.getAttribute('data-original') || el.innerText;
        el.setAttribute('data-original', original);
        try {
          const res = await fetch(`https://translation.googleapis.com/language/translate/v2?key=YOUR_API_KEY`, {
            method:"POST",
            headers:{"Content-Type":"application/json"},
            body:JSON.stringify({q:original,target:lang})
          });
          const data = await res.json();
          if (data.data && data.data.translations) {
            el.innerText = data.data.translations[0].translatedText;
          }
        } catch(e){console.error(e);}
      }
    }
  </script>
</body>
</html>
  <!-- LEARNING MODULES SECTION -->
  <section id="modules">
    <h3 class="section-title">Visual & Vernacular Learning</h3>

    <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:24px;max-width:1100px;margin:auto;">
      <div style="background:white;border-radius:var(--radius);box-shadow:var(--shadow);padding:24px;">
        <h4 style="color:var(--blue);margin-bottom:12px;">Opening a Zero-Balance Account</h4>
        <p>Understand the process and documents required for opening a Jan Dhan Yojana account at your nearest bank.</p>
        <a href="https://pmjdy.gov.in/account" target="_blank" style="display:inline-block;margin-top:12px;color:var(--green);font-weight:600;text-decoration:none;">Learn More →</a>
      </div>

      <div style="background:white;border-radius:var(--radius);box-shadow:var(--shadow);padding:24px;">
        <h4 style="color:var(--blue);margin-bottom:12px;">Applying for Welfare Schemes</h4>
        <p>Step-by-step animated guides on accessing key welfare benefits including PM-Kisan and Ayushman Bharat.</p>
        <a href="https://www.india.gov.in/my-government/schemes" target="_blank" style="display:inline-block;margin-top:12px;color:var(--green);font-weight:600;text-decoration:none;">Official Schemes →</a>
      </div>

      <div style="background:white;border-radius:var(--radius);box-shadow:var(--shadow);padding:24px;">
        <h4 style="color:var(--blue);margin-bottom:12px;">Using UPI & Digital Payments Safely</h4>
        <p>Learn digital security basics to prevent scams and use BHIM UPI, Paytm or Google Pay responsibly.</p>
        <a href="https://www.rbi.org.in/Scripts/BS_PressReleaseDisplay.aspx?prid=55411" target="_blank" style="display:inline-block;margin-top:12px;color:var(--green);font-weight:600;text-decoration:none;">RBI Advisory →</a>
      </div>
    </div>
  </section>

  <!-- INTERACTIVE QUIZ SECTION -->
  <section id="quiz">
    <h3 class="section-title">Interactive Reinforcement</h3>
    <div style="max-width:700px;margin:auto;text-align:center;background:white;border-radius:var(--radius);box-shadow:var(--shadow);padding:40px;">
      <p id="quizQuestion" style="font-size:1.1rem;font-weight:500;">What is the minimum age to open a bank savings account in India?</p>
      <div id="quizOptions" style="margin-top:20px;display:flex;flex-direction:column;gap:10px;">
        <button onclick="checkAnswer('12')" class="cta">12 years</button>
        <button onclick="checkAnswer('18')" class="cta">18 years</button>
        <button onclick="checkAnswer('10')" class="cta">10 years</button>
      </div>
      <p id="quizFeedback" style="margin-top:20px;font-weight:600;"></p>
    </div>
  </section>

  <!-- LOCAL RESOURCES SECTION -->
  <section id="resources">
    <h3 class="section-title">Practical Application & Local Resources</h3>
    <p style="text-align:center;max-width:750px;margin:auto;margin-bottom:30px;">Find nearby Bank Mitra and CSC (Common Service Centre) points to take action locally. Verified directories ensure safety and authenticity.</p>
    <div style="text-align:center;">
      <a href="https://bankmitra.bcfi.org.in/" target="_blank" class="cta">Locate Bank Mitra</a>
      <a href="https://csc.gov.in/" target="_blank" class="cta" style="margin-left:12px;">Locate CSC Centre</a>
    </div>
  </section>

  <!-- VOICE-BASED SECTION PLACEHOLDER -->
  <section id="voice">
    <h3 class="section-title">Voice-First & Offline Access</h3>
    <p style="text-align:center;max-width:750px;margin:auto;">Upcoming Feature: Listen to audio lessons and use our voice chatbot to get answers in your language — even offline!</p>
  </section>

  <script>
    // Simple quiz logic
    function checkAnswer(ans) {
      const feedback = document.getElementById('quizFeedback');
      if (ans === '10') {
        feedback.innerText = "✅ Correct! A minor aged 10 or above can open a savings account with a guardian’s consent.";
        feedback.style.color = "green";
      } else {
        feedback.innerText = "❌ Not quite right — try again!";
        feedback.style.color = "red";
      }
    }
  </script>

    <!-- VOICE CHATBOT SECTION -->
  <section id="bankSakhi">
    <h3 class="section-title">Meet Bank Sakhi – Your Voice Guide</h3>

    <div style="max-width:800px;margin:auto;background:white;border-radius:var(--radius);box-shadow:var(--shadow);padding:32px;text-align:center;">
      <p style="margin-bottom:20px;">Ask Bank Sakhi questions like:</p>
      <ul style="list-style:none;padding:0;margin-bottom:24px;">
        <li>🎤 “How can I open a Jan Dhan account?”</li>
        <li>🎤 “What documents are needed for KYC?”</li>
        <li>🎤 “How do I link Aadhaar to my bank account?”</li>
      </ul>

      <button id="startVoice" class="cta">🎙️ Speak Now</button>
      <p id="voiceOutput" style="margin-top:20px;font-weight:500;color:var(--blue);"></p>

      <audio id="audioLesson" controls style="margin-top:24px;width:100%;">
        <source src="https://www.nios.ac.in/media/documents/vocational-courses/audio/BankingBasics.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>

      <a href="https://pmjdy.gov.in/scheme" target="_blank" class="cta" style="margin-top:18px;display:inline-block;">Explore PMJDY Scheme</a>
    </div>
  </section>

  <script>
    // --- Speech Recognition Setup ---
    let recognition;
    if ('webkitSpeechRecognition' in window) {
      recognition = new webkitSpeechRecognition();
      recognition.lang = 'en-IN';
      recognition.continuous = false;
      recognition.interimResults = false;

      recognition.onstart = () => {
        document.getElementById('voiceOutput').innerText = "Listening...";
      };

      recognition.onerror = (e) => {
        document.getElementById('voiceOutput').innerText = "Error: " + e.error;
      };

      recognition.onresult = (event) => {
        const transcript = event.results[0][0].transcript.toLowerCase();
        document.getElementById('voiceOutput').innerText = "You said: " + transcript;
        respondToVoice(transcript);
      };
    }

    document.getElementById('startVoice').addEventListener('click', () => {
      if (recognition) recognition.start();
      else alert("Speech recognition not supported on this browser.");
    });

    // --- Basic Response Logic ---
    function respondToVoice(text) {
      let response = "";
      if (text.includes("jan dhan")) {
        response = "To open a Jan Dhan Yojana account, visit any bank branch with your Aadhaar and PAN. It's free and needs no minimum balance.";
      } else if (text.includes("kyc")) {
        response = "KYC stands for Know Your Customer. You need Aadhaar, PAN, and a passport-size photo to complete it.";
      } else if (text.includes("aadhaar")) {
        response = "Link Aadhaar to your bank account via your bank’s app, ATM, or by submitting a form in-branch.";
      } else {
        response = "I'm still learning! Visit rbi.org.in for verified information.";
      }

      document.getElementById('voiceOutput').innerText = response;

      // Optional Speech Response
      const synth = window.speechSynthesis;
      const utter = new SpeechSynthesisUtterance(response);
      utter.lang = 'en-IN';
      synth.speak(utter);
    }
  </script>

  <!-- OFFLINE ACCESS MESSAGE -->
  <section id="offline">
    <h3 class="section-title">Offline & Low-Data Learning</h3>
    <p style="max-width:700px;margin:auto;text-align:center;">
      Download short audio lessons and guides in your language for offline learning.  
      No login, no personal data, no ads — just knowledge.  
      <br><br>
      <a href="https://rbi.org.in" target="_blank" class="cta">RBI Financial Education →</a>
      <a href="https://nsdcindia.org" target="_blank" class="cta" style="margin-left:12px;">NSDC Skill Courses →</a>
    </p>
  </section>

  <!-- MULTILINGUAL SYSTEM SECTION -->
<section id="language">
  <h3 class="section-title">🌐 Choose Your Language</h3>
  <div style="text-align:center;">
    <select id="langSelect" style="padding:10px 20px;border-radius:8px;font-size:1rem;">
      <option value="en">English</option>
      <option value="hi">हिन्दी</option>
      <option value="ta">தமிழ்</option>
      <option value="te">తెలుగు</option>
      <option value="bn">বাংলা</option>
      <option value="mr">मराठी</option>
      <option value="ml">മലയാളം</option>
      <option value="kn">ಕನ್ನಡ</option>
      <option value="gu">ગુજરાતી</option>
      <option value="or">ଓଡ଼ିଆ</option>
    </select>
  </div>
</section>

<script>
// --- Translation data ---
const translations = {
  en: {
    heroTitle: "Empowering India's Underserved with Financial Knowledge",
    heroDesc: "Bank Bridge is a digital platform bridging the financial literacy gap for every Indian family.",
    learnBtn: "Learn Financial Basics",
    quizTitle: "Interactive Reinforcement",
    voiceTitle: "Voice-First & Offline Access"
  },
  hi: {
    heroTitle: "भारत के वंचित वर्ग को वित्तीय ज्ञान से सशक्त बनाना",
    heroDesc: "बैंक ब्रिज एक डिजिटल प्लेटफ़ॉर्म है जो हर भारतीय परिवार के लिए वित्तीय साक्षरता की खाई को पाटता है।",
    learnBtn: "वित्तीय मूल बातें सीखें",
    quizTitle: "इंटरएक्टिव पुनर्बलन",
    voiceTitle: "वॉइस-फर्स्ट और ऑफलाइन पहुँच"
  },
  ta: {
    heroTitle: "இந்தியாவின் பின்தங்கியவர்களை நிதி அறிவால் வலுப்படுத்தல்",
    heroDesc: "பேங்க் பிரிட்ஜ் இந்திய குடும்பங்களுக்கான நிதி கல்வி தளமாகும்.",
    learnBtn: "நிதி அடிப்படைகளை கற்றுக்கொள்ளுங்கள்",
    quizTitle: "இணைய விளையாட்டுகள்",
    voiceTitle: "குரல் மற்றும் ஆஃப்லைன் அணுகல்"
  },
  te: {
    heroTitle: "భారతదేశం లో వెనుకబడిన వారిని ఆర్థిక జ్ఞానంతో సాధికారితం చేయడం",
    heroDesc: "బ్యాంక్ బ్రిడ్జ్ ప్రతి కుటుంబానికి ఆర్థిక విద్య అందించే వేదిక.",
    learnBtn: "ఆర్థిక ప్రాథమికాలు నేర్చుకోండి",
    quizTitle: "ఇంటరాక్టివ్ క్విజ్",
    voiceTitle: "వాయిస్ & ఆఫ్‌లైన్ యాక్సెస్"
  },
  bn: {
    heroTitle: "ভারতের অবহেলিতদের আর্থিক জ্ঞানে সক্ষম করা",
    heroDesc: "ব্যাঙ্ক ব্রিজ প্রতিটি পরিবারের জন্য একটি আর্থিক শিক্ষা প্ল্যাটফর্ম।",
    learnBtn: "আর্থিক মৌলিক শেখো",
    quizTitle: "ইন্টারেক্টিভ কুইজ",
    voiceTitle: "ভয়েস এবং অফলাইন অ্যাক্সেস"
  },
  mr: {
    heroTitle: "भारतातील वंचितांना आर्थिक ज्ञानाने सबलीकरण",
    heroDesc: "बँक ब्रिज हे प्रत्येक भारतीय कुटुंबासाठी आर्थिक शिक्षण व्यासपीठ आहे.",
    learnBtn: "आर्थिक मूलतत्त्वे शिका",
    quizTitle: "परस्परसंवादी क्विझ",
    voiceTitle: "व्हॉईस आणि ऑफलाइन प्रवेश"
  },
  ml: {
    heroTitle: "ഇന്ത്യയിലെ പിന്നാക്ക വിഭാഗങ്ങളെ ധനകാര്യ അറിവിലൂടെ ശക്തമാക്കുക",
    heroDesc: "ബാങ്ക് ബ്രിഡ്ജ് എല്ലാ കുടുംബങ്ങൾക്കും സാമ്പത്തിക വിദ്യാഭ്യാസ വേദിയാണ്.",
    learnBtn: "ധനകാര്യ അടിസ്ഥാനങ്ങൾ പഠിക്കുക",
    quizTitle: "ഇന്ററാക്ടീവ് ക്വിസ്",
    voiceTitle: "വോയിസ്-ഓഫ്‌ലൈൻ ആക്സസ്"
  },
  kn: {
    heroTitle: "ಭಾರತದ ಹಿಂದುಳಿದವರನ್ನು ಹಣಕಾಸು ಜ್ಞಾನದಿಂದ ಶಕ್ತಿಗೊಳಿಸುವುದು",
    heroDesc: "ಬ್ಯಾಂಕ್ ಬ್ರಿಡ್ಜ್ ಪ್ರತಿ ಕುಟುಂಬಕ್ಕೂ ಹಣಕಾಸು ಶಿಕ್ಷಣ ನೀಡುವ ವೇದಿಕೆ.",
    learnBtn: "ಹಣಕಾಸು ಮೂಲಭೂತಗಳನ್ನು ಕಲಿಯಿರಿ",
    quizTitle: "ಅಂತರಕ್ರಿಯಾತ್ಮಕ ಪ್ರಶ್ನೆ",
    voiceTitle: "ವಾಯ್ಸ್ ಮತ್ತು ಆಫ್‌ಲೈನ್ ಪ್ರವೇಶ"
  },
  gu: {
    heroTitle: "ભારતના વંચિતોને આર્થિક જ્ઞાનથી સશક્ત બનાવવું",
    heroDesc: "બેંક બ્રિજ દરેક પરિવારમાં આર્થિક શિક્ષણ પૂરું પાડે છે.",
    learnBtn: "આર્થિક મૂળભૂત બાબતો શીખો",
    quizTitle: "ઇન્ટરએક્ટિવ ક્વિઝ",
    voiceTitle: "વોઇસ અને ઑફલાઇન ઍક્સેસ"
  },
  or: {
    heroTitle: "ଭାରତର ଅବହେଳିତଙ୍କୁ ଆର୍ଥିକ ଜ୍ଞାନରେ ସଶକ୍ତ କରା",
    heroDesc: "ବ୍ୟାଙ୍କ ବ୍ରିଜ ପ୍ରତ୍ୟେକ ପରିବାର ପାଇଁ ଆର୍ଥିକ ଶିକ୍ଷା ମଞ୍ଚ ।",
    learnBtn: "ଆର୍ଥିକ ମୂଳ ଶିଖନ୍ତୁ",
    quizTitle: "ଇଣ୍ଟରାକ୍ଟିଭ କୁଇଜ୍",
    voiceTitle: "ଭଏସ୍ ଏବଂ ଅଫଲାଇନ୍ ଆକ୍ସେସ୍"
  }
};

// --- Apply Translation ---
function applyLang(lang) {
  const t = translations[lang];
  if (!t) return;

  const heroTitle = document.querySelector('#hero h1');
  const heroDesc = document.querySelector('#hero p');
  const learnBtn = document.querySelector('#hero .cta');
  const quizTitle = document.querySelector('#quiz .section-title');
  const voiceTitle = document.querySelector('#voice .section-title');

  if (heroTitle) heroTitle.innerText = t.heroTitle;
  if (heroDesc) heroDesc.innerText = t.heroDesc;
  if (learnBtn) learnBtn.innerText = t.learnBtn;
  if (quizTitle) quizTitle.innerText = t.quizTitle;
  if (voiceTitle) voiceTitle.innerText = t.voiceTitle;

  localStorage.setItem('bankbridge_lang', lang);
}

// --- Language Selector ---
const langSelect = document.getElementById('langSelect');
langSelect.addEventListener('change', e => applyLang(e.target.value));

// Load saved preference
const savedLang = localStorage.getItem('bankbridge_lang') || 'en';
langSelect.value = savedLang;
applyLang(savedLang);
</script>
