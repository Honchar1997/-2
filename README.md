<!DOCTYPE html>
<html lang="he" dir="rtl">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>LifePilot - מצפן לחיים</title>
  <link href="https://fonts.googleapis.com/css2?family=Assistant:wght@400;600;700&display=swap" rel="stylesheet" />
  <script src="https://kit.fontawesome.com/a2e00b8a07.js" crossorigin="anonymous"></script>
  <style>
    /* בסיס */
    body {
      margin: 0;
      font-family: 'Assistant', sans-serif;
      background: linear-gradient(135deg, #e0f7fa, #ffffff);
      color: #004d40;
      direction: rtl;
      scroll-behavior: smooth;
    }

    a {
      text-decoration: none;
      color: inherit;
      cursor: pointer;
    }

    /* ניווט עליון */
    nav {
      background-color: #00acc1;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 10px 20px;
      position: sticky;
      top: 0;
      z-index: 100;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
    }

    nav .nav-links {
      display: flex;
      gap: 25px;
      align-items: center;
    }

    nav .nav-links a {
      color: white;
      font-weight: 600;
      font-size: 1.05rem;
      transition: color 0.3s ease;
    }

    nav .nav-links a:hover {
      color: #b2ebf2;
    }

    nav .language-switch {
      background: white;
      border: none;
      border-radius: 20px;
      padding: 6px 12px;
      font-weight: 600;
      cursor: pointer;
      color: #00acc1;
      transition: background-color 0.3s ease;
    }

    nav .language-switch:hover {
      background-color: #b2ebf2;
    }

    /* כותרת ראשית */
    header {
      background-color: #00acc1;
      padding: 25px 20px;
      text-align: center;
      color: white;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
    }

    header h1 {
      margin: 0;
      font-size: 2.8rem;
      font-weight: 700;
    }

    .tagline {
      font-size: 1.3rem;
      margin-top: 6px;
      font-weight: 400;
    }

    /* אזור וידאו */
    section.video-section {
      text-align: center;
      margin: 40px 20px;
    }

    section.video-section iframe {
      width: 100%;
      max-width: 800px;
      height: 450px;
      border-radius: 12px;
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.2);
    }

    /* יתרונות */
    section.features {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 40px;
      margin: 40px 20px;
    }

    .feature {
      background-color: #ffffff;
      border-radius: 12px;
      padding: 30px;
      width: 300px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      text-align: center;
      transition: transform 0.3s ease;
    }

    .feature:hover {
      transform: translateY(-5px);
    }

    .feature i {
      font-size: 3rem;
      color: #00838f;
      margin-bottom: 10px;
    }

    .feature h3 {
      margin-bottom: 10px;
      color: #00796b;
      font-weight: 600;
    }

    /* תמונות אפליקציה */
    section.images-section {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      padding: 20px;
    }

    section.images-section img {
      max-width: 300px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    }

    /* קבלת ייעוץ מקצועי */
    section.cta-section {
      background-color: #b2ebf2;
      padding: 40px 20px;
      text-align: center;
      margin-top: 40px;
    }

    section.cta-section h2 {
      color: #006064;
      margin-bottom: 20px;
      font-weight: 700;
      font-size: 1.8rem;
    }

    section.cta-section form {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 15px;
      max-width: 400px;
      margin: 0 auto;
    }

    section.cta-section input,
    section.cta-section textarea {
      padding: 12px;
      width: 100%;
      border-radius: 8px;
      border: 1px solid #80deea;
      font-size: 1rem;
      font-family: 'Assistant', sans-serif;
      resize: vertical;
    }

    section.cta-section textarea {
      min-height: 100px;
    }

    section.cta-section button {
      padding: 12px 24px;
      background-color: #00acc1;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 1.1rem;
      cursor: pointer;
      transition: background-color 0.3s ease;
      font-weight: 600;
    }

    section.cta-section button:hover {
      background-color: #00838f;
    }

    /* מי אנחנו */
    section.about-us {
      background: white;
      padding: 40px 20px;
      margin: 40px 20px;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      text-align: center;
    }

    section.about-us h2 {
      color: #006064;
      margin-bottom: 30px;
      font-weight: 700;
      font-size: 2rem;
    }

    .founders {
      display: flex;
      justify-content: center;
      gap: 40px;
      flex-wrap: wrap;
    }

    .founder {
      background: #e0f7fa;
      padding: 20px;
      border-radius: 10px;
      width: 250px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12);
      text-align: center;
      font-weight: 600;
      color: #004d40;
      transition: background-color 0.3s ease;
    }

    .founder:hover {
      background-color: #00acc1;
      color: white;
      cursor: default;
    }

    .founder h3 {
      margin-top: 0;
      margin-bottom: 8px;
      font-weight: 700;
    }

    /* מה אנחנו נותנים */
    section.services {
      background: #b2ebf2;
      padding: 40px 20px;
      margin: 40px 20px;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      text-align: center;
    }

    section.services h2 {
      color: #006064;
      margin-bottom: 30px;
      font-weight: 700;
      font-size: 2rem;
    }

    .service-types {
      display: flex;
      justify-content: center;
      gap: 60px;
      flex-wrap: wrap;
    }

    .service-type {
      background: white;
      border-radius: 10px;
      padding: 30px 25px;
      width: 320px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.12);
      font-weight: 600;
      color: #004d40;
      transition: box-shadow 0.3s ease;
      text-align: center;
    }

    .service-type:hover {
      box-shadow: 0 5px 20px rgba(0, 172, 193, 0.6);
    }

    .service-type h3 {
      font-size: 1.5rem;
      margin-bottom: 12px;
      font-weight: 700;
    }

    /* הורדת אפליקציה */
    section.download-app {
      text-align: center;
      margin: 50px 20px;
    }

    section.download-app h2 {
      color: #006064;
      font-weight: 700;
      margin-bottom: 30px;
      font-size: 2rem;
    }

    .download-buttons {
      display: flex;
      justify-content: center;
      gap: 30px;
      flex-wrap: wrap;
    }

    .download-button {
      background-color: #00acc1;
      color: white;
      border-radius: 50px;
      padding: 15px 25px;
      font-weight: 700;
      font-size: 1.1rem;
      box-shadow: 0 3px 12px rgba(0, 0, 0, 0.25);
      display: flex;
      align-items: center;
      gap: 12px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .download-button:hover {
      background-color: #00838f;
    }

    .download-button i {
      font-size: 1.5rem;
    }

    /* בלוג וטיפים */
    section.blog {
      background: white;
      margin: 40px 20px;
      padding: 40px 20px;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.12);
      max-width: 1000px;
      margin-left: auto;
      margin-right: auto;
    }

    section.blog h2 {
      color: #006064;
      font-weight: 700;
      margin-bottom: 30px;
      font-size: 2rem;
      text-align: center;
    }

    .blog-posts {
      display: flex;
      gap: 30px;
      flex-wrap: wrap;
      justify-content: center;
    }

    .blog-post {
      width: 300px;
      background-color: #e0f7fa;
      border-radius: 12px;
      padding: 20px;
      box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
      font-weight: 600;
      color: #004d40;
      transition: background-color 0.3s ease;
      cursor: pointer;
    }

    .blog-post:hover {
      background-color: #00acc1;
      color: white;
    }

    .blog-post h3 {
      margin-top: 0;
      margin-bottom: 10px;
      font-weight: 700;
      font-size: 1.3rem;
    }

    .blog-post p {
      font-weight: 400;
      font-size: 1rem;
      line-height: 1.4;
    }

    /* רספונסיביות */
    @media (max-width: 900px) {
      section.features,
      section.blog .blog-posts,
      section.services .service-types,
      section.about-us .founders {
        flex-direction: column;
        align-items: center;
      }

      section.features .feature,
      section.blog .blog-post,
      section.services .service-type,
      section.about-us .founder {
        width: 90%;
        max-width: 350px;
      }

      nav {
        flex-wrap: wrap;
      }

      nav .nav-links {
        gap: 15px;
        margin-top: 10px;
        width: 100%;
        justify-content: center;
      }
    }
  </style>
</head>

<body>

  <!-- ניווט עליון -->
  <nav>
    <div class="nav-links" id="navLinks">
      <a href="#features-section">יתרונות</a>
      <a href="#about-us">מי אנחנו</a>
      <a href="#services">מה אנחנו נותנים</a>
      <a href="#blog">בלוג</a>
      <a href="#cta-section">לקבל ייעוץ מקצועי</a>
      <a href="#download-app">הורדת אפליקציה</a>
    </div>
    <button class="language-switch" id="languageSwitchBtn" aria-label="Switch language">English</button>
  </nav>

  <!-- כותרת ראשית -->
  <header>
    <h1 id="mainTitle">LifePilot - מצפן לחיים</h1>
    <p class="tagline" id="tagline">הדרך הנכונה לניהול זמן ומשימות</p>
  </header>

  <!-- וידאו -->
  <section class="video-section">
    <iframe id="introVideo" src="https://www.youtube.com/embed/bIxDy0HD7OQ" title="LifePilot Intro Video" frameborder="0" allowfullscreen></iframe>
  </section>

  <!-- יתרונות -->
  <section class="features" id="features-section">
    <div class="feature">
      <i class="fas fa-bolt"></i>
      <h3>יעילות מקסימלית</h3>
      <p>ניהול זמן ומשימות מדויק ויעיל.</p>
    </div>
    <div class="feature">
      <i class="fas fa-users"></i>
      <h3>עיצוב אינטואיטיבי</h3>
      <p>ממשק נוח ומזמין לשימוש יומיומי.</p>
    </div>
    <div class="feature">
      <i class="fas fa-cloud-upload-alt"></i>
      <h3>סנכרון בענן</h3>
      <p>כל המשימות שלך זמינות בכל מכשיר.</p>
    </div>
  </section>

  <!-- תמונות אפליקציה -->
  <section class="images-section">
    <img src="https://via.placeholder.com/300x600?text=מסך+ראשי" alt="מסך ראשי באפליקציה" />
    <img src="https://via.placeholder.com/300x600?text=ניהול+משימות" alt="ניהול משימות באפליקציה" />
  </section>

  <!-- מי אנחנו -->
  <section class="about-us" id="about-us">
    <h2>מי אנחנו</h2>
    <div class="founders">
      <div class="founder" title="איליה גונצ'ר - מייסד ומנכ"ל">
        <h3>איליה גונצ'ר</h3>
        <p>מייסד ומנכ"ל, עם ניסיון צבאי בניהול מורכב ומובילות צוותים.</p>
      </div>
      <div class="founder" title="אביחי זקן - סמנכ"ל שיווק">
        <h3>אביחי זקן</h3>
        <p>סמנכ"ל שיווק, מומחה לקידום והפצה של טכנולוגיות חדשניות.</p>
      </div>
      <div class="founder" title="טל חקלאי - מנהל פיתוח מוצר">
        <h3>טל חקלאי</h3>
        <p>מנהל פיתוח מוצר, מוביל תהליכי עיצוב ופיתוח חוויית משתמש.</p>
      </div>
    </div>
  </section>

  <!-- מה אנחנו נותנים -->
  <section class="services" id="services">
    <h2>מה אנחנו נותנים</h2>
    <div class="service-types">
      <div class="service-type">
        <h3>B2C – פתרונות פרטיים</h3>
        <p>אפליקציה לניהול זמן ומשימות לפרטים, עם תזכורות חכמות, דוחות התקדמות וקהילה תומכת.</p>
      </div>
      <div class="service-type">
        <h3>B2B – פתרונות עסקיים</h3>
        <p>פלטפורמה לניהול פרויקטים ותקשורת צוותית, אינטגרציה עם מערכות CRM וכלים ארגוניים.</p>
      </div>
    </div>
  </section>

  <!-- בלוג וטיפים -->
  <section class="blog" id="blog">
    <h2>בלוג וטיפים לניהול זמן ומשמימות</h2>
    <div class="blog-posts">
      <div class="blog-post" tabindex="0" role="article" aria-label="איך לנהל זמן בצורה אפקטיבית">
        <h3>איך לנהל זמן בצורה אפקטיבית</h3>
        <p>טיפים ועקרונות לניהול יום עבודה יעיל יותר עם LifePilot.</p>
      </div>
      <div class="blog-post" tabindex="0" role="article" aria-label="טיפים למניעת דחיינות">
        <h3>טיפים למניעת דחיינות</h3>
        <p>איך להתמודד עם דחיינות ולהשיג תוצאות בעזרת האפליקציה שלנו.</p>
      </div>
      <div class="blog-post" tabindex="0" role="article" aria-label="איך האפליקציה מקלה על החיים">
        <h3>איך האפליקציה מקלה על החיים</h3>
        <p>היכרות עם כלים ופיצ'רים שיחסכו לך זמן ויעלו את הפרודוקטיביות.</p>
      </div>
    </div>
  </section>

  <!-- לקבל ייעוץ מקצועי -->
  <section class="cta-section" id="cta-section">
    <h2>לקבל ייעוץ מקצועי</h2>
    <form id="consultationForm" aria-label="טופס לקבלת ייעוץ מקצועי">
      <input type="text" id="nameInput" name="name" placeholder="שם מלא" required aria-required="true" />
      <input type="email" id="emailInput" name="email" placeholder="אימייל" required aria-required="true" />
      <textarea id="messageInput" name="message" placeholder="תיאור קצר של הצורך שלך" required aria-required="true"></textarea>
      <button type="submit" aria-label="שלח בקשת ייעוץ">שלח</button>
      <p id="formFeedback" role="alert" aria-live="assertive" style="margin-top: 12px;"></p>
    </form>
  </section>

  <!-- הורדת אפליקציה -->
  <section class="download-app" id="download-app">
    <h2>הורדת האפליקציה</h2>
    <div class="download-buttons">
      <a href="https://play.google.com/store/apps/details?id=com.lifePilot.app" target="_blank" rel="noopener" class="download-button" aria-label="הורדה מגוגל פליי">
        <i class="fab fa-google-play"></i> Google Play
      </a>
      <a href="https://apps.apple.com/app/lifepilot/id1234567890" target="_blank" rel="noopener" class="download-button" aria-label="הורדה מאפסטור">
        <i class="fab fa-apple"></i> App Store
      </a>
    </div>
  </section>

  <script>
    // שינוי שפה בסיסי (עברית / אנגלית)
    const langBtn = document.getElementById('languageSwitchBtn');

    const texts = {
      he: {
        mainTitle: "LifePilot - מצפן לחיים",
        tagline: "הדרך הנכונה לניהול זמן ומשימות",
        navLinks: ["יתרונות", "מי אנחנו", "מה אנחנו נותנים", "בלוג", "לקבל ייעוץ מקצועי", "הורדת אפליקציה"],
        features: [
          { title: "יעילות מקסימלית", desc: "ניהול זמן ומשימות מדויק ויעיל." },
          { title: "עיצוב אינטואיטיבי", desc: "ממשק נוח ומזמין לשימוש יומיומי." },
          { title: "סנכרון בענן", desc: "כל המשימות שלך זמינות בכל מכשיר." }
        ],
        aboutUsTitle: "מי אנחנו",
        servicesTitle: "מה אנחנו נותנים",
        services: [
          { title: "B2C – פתרונות פרטיים", desc: "אפליקציה לניהול זמן ומשימות לפרטים, עם תזכורות חכמות, דוחות התקדמות וקהילה תומכת." },
          { title: "B2B – פתרונות עסקיים", desc: "פלטפורמה לניהול פרויקטים ותקשורת צוותית, אינטגרציה עם מערכות CRM וכלים ארגוניים." }
        ],
        blogTitle: "בלוג וטיפים לניהול זמן ומשמימות",
        blogPosts: [
          { title: "איך לנהל זמן בצורה אפקטיבית", desc: "טיפים ועקרונות לניהול יום עבודה יעיל יותר עם LifePilot." },
          { title: "טיפים למניעת דחיינות", desc: "איך להתמודד עם דחיינות ולהשיג תוצאות בעזרת האפליקציה שלנו." },
          { title: "איך האפליקציה מקלה על החיים", desc: "היכרות עם כלים ופיצ'רים שיחסכו לך זמן ויעלו את הפרודוקטיביות." }
        ],
        ctaTitle: "לקבל ייעוץ מקצועי",
        formPlaceholders: {
          name: "שם מלא",
          email: "אימייל",
          message: "תיאור קצר של הצורך שלך"
        },
        formSubmitBtn: "שלח",
        downloadTitle: "הורדת האפליקציה",
        downloadGooglePlay: "Google Play",
        downloadAppStore: "App Store"
      },
      en: {
        mainTitle: "LifePilot - Your Life Compass",
        tagline: "The right way to manage time and tasks",
        navLinks: ["Features", "About Us", "Services", "Blog", "Get Professional Advice", "Download App"],
        features: [
          { title: "Maximum Efficiency", desc: "Precise and efficient time and task management." },
          { title: "Intuitive Design", desc: "A user-friendly interface for daily use." },
          { title: "Cloud Sync", desc: "Your tasks available on all devices." }
        ],
        aboutUsTitle: "About Us",
        servicesTitle: "Our Offerings",
        services: [
          { title: "B2C – Personal Solutions", desc: "An app for personal time and task management, with smart reminders, progress reports, and a supportive community." },
          { title: "B2B – Business Solutions", desc: "A platform for project management and team communication, integration with CRM systems and organizational tools." }
        ],
        blogTitle: "Blog & Tips for Time and Task Management",
        blogPosts: [
          { title: "How to Manage Time Effectively", desc: "Tips and principles for a more efficient workday with LifePilot." },
          { title: "Tips to Prevent Procrastination", desc: "How to tackle procrastination and achieve results with our app." },
          { title: "How the App Makes Life Easier", desc: "An introduction to tools and features that save you time and boost productivity." }
        ],
        ctaTitle: "Get Professional Advice",
        formPlaceholders: {
          name: "Full Name",
          email: "Email",
          message: "Brief description of your need"
        },
        formSubmitBtn: "Send",
        downloadTitle: "Download the App",
        downloadGooglePlay: "Google Play",
        downloadAppStore: "App Store"
      }
    };

    let currentLang = 'he';

    function updateLanguage(lang) {
      currentLang = lang;
      const t = texts[lang];

      document.getElementById('mainTitle').textContent = t.mainTitle;
      document.getElementById('tagline').textContent = t.tagline;

      const navLinks = document.querySelectorAll('.nav-links a');
      navLinks.forEach((link, i) => {
        link.textContent = t.navLinks[i];
      });

      const features = document.querySelectorAll('.feature h3');
      const featuresDesc = document.querySelectorAll('.feature p');
      features.forEach((f, i) => f.textContent = t.features[i].title);
      featuresDesc.forEach((d, i) => d.textContent = t.features[i].desc);

      document.querySelector('#about-us h2').textContent = t.aboutUsTitle;

      const serviceTitles = document.querySelectorAll('.service-type h3');
      const serviceDesc = document.querySelectorAll('.service-type p');
      serviceTitles.forEach((s, i) => s.textContent = t.services[i].title);
      serviceDesc.forEach((d, i) => d.textContent = t.services[i].desc);
      document.querySelector('#services h2').textContent = t.servicesTitle;

      document.querySelector('#blog h2').textContent = t.blogTitle;
      const blogPostsTitles = document.querySelectorAll('.blog-post h3');
      const blogPostsDesc = document.querySelectorAll('.blog-post p');
      blogPostsTitles.forEach((b, i) => b.textContent = t.blogPosts[i].title);
      blogPostsDesc.forEach((b, i) => b.textContent = t.blogPosts[i].desc);

      document.querySelector('#cta-section h2').textContent = t.ctaTitle;
      document.getElementById('nameInput').placeholder = t.formPlaceholders.name;
      document.getElementById('emailInput').placeholder = t.formPlaceholders.email;
      document.getElementById('messageInput').placeholder = t.formPlaceholders.message;
      document.querySelector('#cta-section button').textContent = t.formSubmitBtn;

      document.querySelector('#download-app h2').textContent = t.downloadTitle;
      const downloadButtons = document.querySelectorAll('.download-button');
      downloadButtons[0].innerHTML = `<i class="fab fa-google-play"></i> ${t.downloadGooglePlay}`;
      downloadButtons[1].innerHTML = `<i class="fab fa-apple"></i> ${t.downloadAppStore}`;

      langBtn.textContent = lang === 'he' ? 'English' : 'עברית';
    }

    langBtn.addEventListener('click', () => {
      updateLanguage(currentLang === 'he' ? 'en' : 'he');
    });

    // אתחול לשפה העברית
    updateLanguage('he');

    // טיפול בטופס
    document.getElementById('consultationForm').addEventListener('submit', function (e) {
      e.preventDefault();
      const name = this.name.value.trim();
      const email = this.email.value.trim();
      const message = this.message.value.trim();
      const feedback = document.getElementById('formFeedback');

      if (!name || !email || !message) {
        feedback.textContent = currentLang === 'he' ? 'אנא מלא את כל השדות.' : 'Please fill in all fields.';
        feedback.style.color = 'red';
        return;
      }

      // כאן אפשר להוסיף שליחה לשרת או API

      feedback.textContent = currentLang === 'he' ? 'תודה, ניצור איתך קשר בקרוב.' : 'Thank you, we will contact you soon.';
      feedback.style.color = 'green';
      this.reset();
    });
  </script>

</body>

</html>
