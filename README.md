<!DOCTYPE html>
<html lang="uz">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>KIU</title>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="styles.css" />
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  </head>
  <body>
    <div class="page-shell">
      <header class="topbar">
        <div class="brand">
          <div class="brand-mark">BILIM</div>
          <span>Bilim sinovi</span>
        </div>

        <nav class="nav">
          <a href="#home">Bosh sahifa</a>
          <a href="#registerSection">Ro‘yxatdan o‘tish</a>
          <a href="#dashboardSection">Dashboard</a>
        </nav>
      </header>

      <main>
        <section id="home" class="hero">
          <div class="hero-copy">
            <span class="eyebrow">Universitet ilmiy tadqiqoti</span>
            <h1>BILIM sinovi</h1>
            <p>
              Talabalar o‘qish jarayonini ilmiy usulda o‘rganish va turli
              o‘qish metodlarining samaradorligini tajriba orqali aniqlash
              uchun yaratilgan platforma.
            </p>
            <button id="startProjectBtn" class="primary-btn">
              Tadqiqotni boshlash
            </button>
          </div>

          <div class="hero-panel">
            <div class="stat-card">
              <span>O‘rganilayotgan metodlar</span>
              <strong>3 ta</strong>
            </div>
            <div class="stat-card">
              <span>Testlar soni</span>
              <strong>2 bosqich</strong>
            </div>
            <div class="stat-card">
              <span>Natija tahlili</span>
              <strong>Real vaqt</strong>
            </div>
          </div>
        </section>

        <section id="registerSection" class="panel">
          <div class="section-title">
            <h2>Ro‘yxatdan o‘tish</h2>
            <p>Talabani tizimga kiritib olish uchun ma’lumotlarni to‘ldiring.</p>
          </div>

          <form id="registerForm" class="register-form">
            <div class="field-group">
              <label for="fullName">Ism</label>
              <input id="fullName" name="fullName" type="text" required />
            </div>

            <div class="field-group">
              <label for="faculty">Fakultet</label>
              <select id="faculty" name="faculty" required>
                <option value="">Tanlang</option>
                <option value="IT va axborot texnologiyalari">IT va axborot texnologiyalari</option>
                <option value="Tibbiyot">Tibbiyot</option>
                <option value="Iqtisodiyot">Iqtisodiyot</option>
                <option value="Gumanitar fanlar">Gumanitar fanlar</option>
                <option value="Texnika">Texnika</option>
              </select>
            </div>

            <div class="field-group">
              <label for="course">Kurs</label>
              <select id="course" name="course" required>
                <option value="">Tanlang</option>
                <option value="1-kurs">1-kurs</option>
                <option value="2-kurs">2-kurs</option>
                <option value="3-kurs">3-kurs</option>
                <option value="4-kurs">4-kurs</option>
              </select>
            </div>

            <div class="field-group">
              <label for="group">Guruh</label>
              <input id="group" name="group" type="text" required />
            </div>

            <button type="submit" class="primary-btn">Davom etish</button>
          </form>
        </section>

        <section id="baselineSection" class="panel hidden">
          <div class="section-title">
            <h2>Boshlang‘ich test</h2>
            <p>Quyidagi savollar bilim darajasini aniqlash uchun beriladi.</p>
          </div>

          <div id="baselineQuiz" class="quiz-list"></div>
          <button id="submitBaselineBtn" class="primary-btn">
            Natijani saqlash
          </button>
        </section>

        <section id="experimentSection" class="panel hidden">
          <div class="section-title">
            <h2>O‘qish metodlari tajribasi</h2>
            <p>Tanlangan metoddan foydalangan holda ma’lum vaqt davomida o‘rganing.</p>
          </div>

          <div class="method-grid">
            <button class="method-card" data-method="simple">
              <span class="method-label">A</span>
              <h3>Oddiy o‘qish</h3>
              <p>Matnni to‘liq va diqqat bilan o‘rganish.</p>
            </button>

            <button class="method-card" data-method="test">
              <span class="method-label">B</span>
              <h3>Test orqali takrorlash</h3>
              <p>Bir qancha savol va javob orqali mustahkamlash.</p>
            </button>

            <button class="method-card" data-method="interval">
              <span class="method-label">C</span>
              <h3>Interval bilan takrorlash</h3>
              <p>Vaqt oralig‘ida takrorlash orqali yodda saqlash.</p>
            </button>
          </div>

          <div class="experiment-box">
            <p id="experimentTimer">Tajriba vaqti: 00:00</p>

            <div class="experiment-actions">
              <button id="startMethodBtn" class="secondary-btn">
                Tajriba boshlash
              </button>
              <button id="goToFinalBtn" class="primary-btn hidden">
                Yakuniy testga o‘tish
              </button>
            </div>
          </div>
        </section>

        <section id="finalSection" class="panel hidden">
          <div class="section-title">
            <h2>Yakuniy test</h2>
            <p>Tajriba tugagach, bilim darajasi yana baholanadi.</p>
          </div>

          <div id="finalQuiz" class="quiz-list"></div>
          <button id="submitFinalBtn" class="primary-btn">
            Natijani hisoblash
          </button>
        </section>

        <section id="dashboardSection" class="panel hidden">
          <div class="section-title">
            <h2>Dashboard va statistik tahlil</h2>
            <p>Natijalar grafiklar orqali ko‘rsatiladi.</p>
          </div>

          <div class="summary-grid">
            <div class="summary-card">
              <span>Boshlang‘ich natija</span>
              <strong id="initialScoreValue">0%</strong>
            </div>
            <div class="summary-card">
              <span>Yakuniy natija</span>
              <strong id="finalScoreValue">0%</strong>
            </div>
            <div class="summary-card">
              <span>O‘sish foizi</span>
              <strong id="growthValue">0%</strong>
            </div>
            <div class="summary-card">
              <span>O‘rtacha vaqt</span>
              <strong id="avgTimeValue">00:00</strong>
            </div>
            <div class="summary-card">
              <span>Xatolar</span>
              <strong id="errorValue">0</strong>
            </div>
          </div>

          <div class="chart-wrap">
            <canvas id="resultChart"></canvas>
          </div>

          <div id="summaryText" class="summary-text"></div>
        </section>
      </main>
    </div>

    <script src="app.js"></script>
  </body>
</html>
