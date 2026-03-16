# shivees
enehuu website ni shiveeschded zoriulav
<!DOCTYPE html>
<html lang="mn">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>InkReserve | Шивээсний цаг захиалга</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background: #0b0b0f;
      color: #fff;
      overflow-x: hidden;
      line-height: 1.5;
    }

    img {
      max-width: 100%;
      display: block;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    .container {
      width: min(92%, 1200px);
      margin: auto;
    }

    /* HEADER */
    header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: rgba(10, 10, 15, 0.92);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(255,255,255,0.06);
    }

    .nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 16px;
      padding: 14px 0;
      flex-wrap: wrap;
    }

    .logo {
      font-size: clamp(22px, 4vw, 28px);
      font-weight: 800;
      letter-spacing: 1px;
      color: #ff2e63;
      white-space: nowrap;
    }

    .nav-links {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
      justify-content: flex-end;
      font-size: 14px;
      color: #ddd;
    }

    .nav-links a {
      padding: 8px 12px;
      border-radius: 999px;
      transition: 0.3s ease;
    }

    .nav-links a:hover {
      color: #ff2e63;
      background: rgba(255,255,255,0.05);
    }

    /* HERO */
    .hero {
      min-height: 85vh;
      display: flex;
      align-items: center;
      padding: 60px 0;
      background:
        linear-gradient(rgba(8,8,12,0.65), rgba(8,8,12,0.9)),
        url('https://images.unsplash.com/photo-1542727365-19732a80dcfd?auto=format&fit=crop&w=1600&q=80') center/cover no-repeat;
    }

    .hero-content {
      max-width: 700px;
      animation: fadeUp 1s ease;
    }

    .hero h1 {
      font-size: clamp(32px, 7vw, 62px);
      line-height: 1.1;
      margin-bottom: 16px;
    }

    .hero h1 span {
      color: #ff2e63;
    }

    .hero p {
      color: #d1d1d1;
      font-size: clamp(15px, 3vw, 18px);
      line-height: 1.7;
      margin-bottom: 26px;
    }

    .hero-btns {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }

    .btn {
      padding: 14px 22px;
      border-radius: 999px;
      border: none;
      cursor: pointer;
      font-weight: 700;
      transition: 0.3s ease;
      font-size: 15px;
      min-height: 48px;
      width: auto;
    }

    .btn-primary {
      background: #ff2e63;
      color: white;
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 24px rgba(255, 46, 99, 0.35);
    }

    .btn-secondary {
      background: transparent;
      color: white;
      border: 1px solid rgba(255,255,255,0.18);
    }

    .btn-secondary:hover {
      background: rgba(255,255,255,0.06);
    }

    /* SECTIONS */
    section {
      padding: 70px 0;
    }

    .section-title {
      font-size: clamp(28px, 6vw, 38px);
      margin-bottom: 12px;
      text-align: center;
      line-height: 1.2;
    }

    .section-subtitle {
      text-align: center;
      color: #bdbdbd;
      max-width: 700px;
      margin: 0 auto 36px;
      line-height: 1.7;
      font-size: clamp(14px, 3vw, 16px);
      padding: 0 6px;
    }

    /* ARTISTS */
    .artists-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 18px;
    }

    .artist-card {
      background: #13131a;
      border: 1px solid rgba(255,255,255,0.06);
      border-radius: 20px;
      overflow: hidden;
      transition: 0.35s ease;
      cursor: pointer;
    }

    .artist-card:hover {
      transform: translateY(-6px);
      border-color: rgba(255, 46, 99, 0.35);
      box-shadow: 0 14px 30px rgba(0,0,0,0.25);
    }

    .artist-card.selected {
      border: 2px solid #ff2e63;
      box-shadow: 0 0 0 4px rgba(255,46,99,0.12);
    }

    .artist-card img {
      width: 100%;
      height: clamp(220px, 40vw, 280px);
      object-fit: cover;
    }

    .artist-info {
      padding: 16px;
    }

    .artist-info h3 {
      margin-bottom: 8px;
      font-size: clamp(18px, 4vw, 22px);
    }

    .artist-info p {
      color: #bbb;
      font-size: 14px;
      line-height: 1.6;
    }

    /* BOOKING */
    .booking-wrap {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 22px;
    }

    .booking-card, .summary-card {
      background: #13131a;
      border: 1px solid rgba(255,255,255,0.06);
      border-radius: 22px;
      padding: 22px;
      min-width: 0;
    }

    .booking-card h3, .summary-card h3 {
      margin-bottom: 18px;
      font-size: clamp(22px, 4vw, 26px);
    }

    .form-group {
      margin-bottom: 18px;
    }

    .form-group label {
      display: block;
      margin-bottom: 8px;
      color: #ddd;
      font-weight: 600;
      font-size: 14px;
    }

    input, select, textarea {
      width: 100%;
      padding: 14px 14px;
      border-radius: 14px;
      border: 1px solid rgba(255,255,255,0.08);
      background: #0f0f15;
      color: white;
      outline: none;
      font-size: 15px;
      min-height: 48px;
    }

    textarea {
      min-height: 120px;
      resize: vertical;
    }

    input:focus, select:focus, textarea:focus {
      border-color: rgba(255,46,99,0.5);
    }

    .time-slots {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
    }

    .time-slot {
      padding: 12px 8px;
      text-align: center;
      border-radius: 14px;
      background: #0f0f15;
      border: 1px solid rgba(255,255,255,0.08);
      cursor: pointer;
      transition: 0.25s ease;
      font-weight: 600;
      min-height: 48px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 14px;
    }

    .time-slot:hover {
      border-color: rgba(255,46,99,0.35);
    }

    .time-slot.selected {
      background: #ff2e63;
      border-color: #ff2e63;
      color: white;
    }

    .summary-list {
      display: flex;
      flex-direction: column;
      gap: 12px;
      margin-bottom: 20px;
    }

    .summary-item {
      background: #0f0f15;
      border-radius: 16px;
      padding: 14px;
      border: 1px solid rgba(255,255,255,0.06);
      word-break: break-word;
    }

    .summary-item span {
      display: block;
      color: #aaa;
      font-size: 13px;
      margin-bottom: 4px;
    }

    .summary-item strong {
      font-size: 15px;
      line-height: 1.5;
    }

    .success-message {
      margin-top: 16px;
      padding: 14px;
      border-radius: 14px;
      background: rgba(31, 189, 95, 0.12);
      border: 1px solid rgba(31, 189, 95, 0.25);
      color: #7ef0a9;
      display: none;
      font-weight: 600;
      font-size: 14px;
    }

    /* FOOTER */
    footer {
      padding: 26px 0;
      border-top: 1px solid rgba(255,255,255,0.06);
      text-align: center;
      color: #aaa;
      background: #09090c;
      font-size: 14px;
    }

    @keyframes fadeUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* TABLET */
    @media (max-width: 900px) {
      .booking-wrap {
        grid-template-columns: 1fr;
      }

      .hero {
        min-height: auto;
        padding: 80px 0 60px;
      }

      .nav {
        justify-content: center;
      }

      .nav-links {
        justify-content: center;
      }
    }

    /* MOBILE */
    @media (max-width: 600px) {
      section {
        padding: 55px 0;
      }

      .nav {
        flex-direction: column;
        align-items: center;
        gap: 10px;
      }

      .nav-links {
        width: 100%;
        justify-content: center;
        gap: 8px;
      }

      .nav-links a {
        font-size: 13px;
        padding: 8px 10px;
      }

      .hero {
        padding: 70px 0 50px;
      }

      .hero-btns {
        flex-direction: column;
        width: 100%;
      }

      .hero-btns a {
        width: 100%;
      }

      .hero-btns .btn {
        width: 100%;
      }

      .artists-grid {
        grid-template-columns: 1fr;
      }

      .booking-card, .summary-card {
        padding: 18px;
        border-radius: 18px;
      }

      .time-slots {
        grid-template-columns: repeat(2, 1fr);
      }

      .btn {
        font-size: 14px;
      }

      footer {
        font-size: 13px;
        line-height: 1.6;
      }
    }

    /* EXTRA SMALL */
    @media (max-width: 380px) {
      .time-slots {
        grid-template-columns: 1fr;
      }

      .nav-links {
        flex-direction: column;
        align-items: center;
      }
    }
  </style>
</head>
<body>

  <header>
    <div class="container nav">
      <div class="logo">InkReserve</div>
      <nav class="nav-links">
        <a href="#artists">Артистууд</a>
        <a href="#booking">Захиалга</a>
        <a href="#contact">Холбоо барих</a>
      </nav>
    </div>
  </header>

  <section class="hero">
    <div class="container hero-content">
      <h1>Өөрийн дараагийн <span>шивээсний цаг</span>-аа захиалаарай</h1>
      <p>
        Өөрт таалагдсан артистaa сонгож, хүссэн өдөр болон цагаа товлоод
        хэдхэн алхмаар шивээсний цагаа баталгаажуулаарай.
      </p>
      <div class="hero-btns">
        <a href="#booking"><button class="btn btn-primary">Цаг захиалах</button></a>
        <a href="#artists"><button class="btn btn-secondary">Артист үзэх</button></a>
      </div>
    </div>
  </section>

  <section id="artists">
    <div class="container">
      <h2 class="section-title">Артистаа сонгоорой</h2>
      <p class="section-subtitle">
        Өөрийн хүссэн загварт тохирох артистaa сонгоорой. Карт дээр дарж артистaa идэвхжүүлнэ.
      </p>

      <div class="artists-grid">
        <div class="artist-card" data-artist="Алекс Нуар">
          <img src="https://images.unsplash.com/photo-1524504388940-b1c1722653e1?auto=format&fit=crop&w=900&q=80" alt="Алекс Нуар">
          <div class="artist-info">
            <h3>Алекс Нуар</h3>
            <p>Blackwork • Fine Line • Минимал, тод контрасттай нарийн хийцтэй шивээс.</p>
          </div>
        </div>

        <div class="artist-card" data-artist="Мика Инк">
          <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&w=900&q=80" alt="Мика Инк">
          <div class="artist-info">
            <h3>Мика Инк</h3>
            <p>Floral • Нарийн шугам • Эмэгтэйлэг, зөөлөн урсгалтай custom дизайн.</p>
          </div>
        </div>

        <div class="artist-card" data-artist="Рекс Шэйд">
          <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&w=900&q=80" alt="Рекс Шэйд">
          <div class="artist-info">
            <h3>Рекс Шэйд</h3>
            <p>Japanese • Realism • Том хэмжээний, сүүдэрлэл сайтай бүтээлүүд.</p>
          </div>
        </div>

        <div class="artist-card" data-artist="Луна Нийдл">
          <img src="https://images.unsplash.com/photo-1488426862026-3ee34a7d66df?auto=format&fit=crop&w=900&q=80" alt="Луна Нийдл">
          <div class="artist-info">
            <h3>Луна Нийдл</h3>
            <p>Colorwork • Neo-traditional • Өнгөлөг, өвөрмөц, илэрхийлэлтэй шивээс.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="booking">
    <div class="container">
      <h2 class="section-title">Шивээсний цагаа захиалаарай</h2>
      <p class="section-subtitle">
        Мэдээллээ бөглөж, стиль, өдөр, цагаа сонгоод захиалгаа илгээгээрэй.
      </p>

      <div class="booking-wrap">
        <div class="booking-card">
          <h3>Захиалгын маягт</h3>

          <div class="form-group">
            <label for="name">Овог нэр</label>
            <input type="text" id="name" placeholder="Нэрээ оруулна уу">
          </div>

          <div class="form-group">
            <label for="phone">Утасны дугаар</label>
            <input type="text" id="phone" placeholder="Утасны дугаараа оруулна уу">
          </div>

          <div class="form-group">
            <label for="style">Шивээсний төрөл</label>
            <select id="style">
              <option value="">Төрөл сонгох</option>
              <option>Fine Line</option>
              <option>Blackwork</option>
              <option>Minimalist</option>
              <option>Japanese</option>
              <option>Realism</option>
              <option>Neo-Traditional</option>
              <option>Colorwork</option>
              <option>Custom Design</option>
            </select>
          </div>

          <div class="form-group">
            <label for="date">Өдөр сонгох</label>
            <input type="date" id="date">
          </div>

          <div class="form-group">
            <label>Цаг сонгох</label>
            <div class="time-slots" id="timeSlots">
              <div class="time-slot">10:00</div>
              <div class="time-slot">11:30</div>
              <div class="time-slot">13:00</div>
              <div class="time-slot">14:30</div>
              <div class="time-slot">16:00</div>
              <div class="time-slot">17:30</div>
            </div>
          </div>

          <div class="form-group">
            <label for="notes">Шивээсний санаа / Тайлбар</label>
            <textarea id="notes" placeholder="Өөрийн шивээсний санаагаа тайлбарлана уу..."></textarea>
          </div>

          <button class="btn btn-primary" style="width:100%;" onclick="bookAppointment()">Цаг захиалах</button>

          <div class="success-message" id="successMessage">
            ✅ Таны захиалга амжилттай илгээгдлээ!
          </div>
        </div>

        <div class="summary-card">
          <h3>Захиалгын мэдээлэл</h3>

          <div class="summary-list">
            <div class="summary-item">
              <span>Сонгосон артист</span>
              <strong id="summaryArtist">Сонгогдоогүй</strong>
            </div>

            <div class="summary-item">
              <span>Шивээсний төрөл</span>
              <strong id="summaryStyle">Сонгогдоогүй</strong>
            </div>

            <div class="summary-item">
              <span>Өдөр</span>
              <strong id="summaryDate">Сонгогдоогүй</strong>
            </div>

            <div class="summary-item">
              <span>Цаг</span>
              <strong id="summaryTime">Сонгогдоогүй</strong>
            </div>
          </div>

          <p style="color:#bdbdbd; line-height:1.8;">
            Зөвлөгөө: Эхлээд артистaa сонгоод, дараа нь төрөл, өдөр, цагаа сонговол илүү хялбар байна.
          </p>
        </div>
      </div>
    </div>
  </section>

  <footer id="contact">
    <div class="container">
      <p>© 2026 InkReserve Tattoo Studio — Орчин үеийн шивээсний цаг захиалгын систем.</p>
    </div>
  </footer>

  <script>
    let selectedArtist = "";
    let selectedTime = "";

    const artistCards = document.querySelectorAll(".artist-card");
    const timeSlots = document.querySelectorAll(".time-slot");
    const styleSelect = document.getElementById("style");
    const dateInput = document.getElementById("date");

    const summaryArtist = document.getElementById("summaryArtist");
    const summaryStyle = document.getElementById("summaryStyle");
    const summaryDate = document.getElementById("summaryDate");
    const summaryTime = document.getElementById("summaryTime");

    artistCards.forEach(card => {
      card.addEventListener("click", () => {
        artistCards.forEach(c => c.classList.remove("selected"));
        card.classList.add("selected");
        selectedArtist = card.dataset.artist;
        summaryArtist.textContent = selectedArtist;
      });
    });

    timeSlots.forEach(slot => {
      slot.addEventListener("click", () => {
        timeSlots.forEach(s => s.classList.remove("selected"));
        slot.classList.add("selected");
        selectedTime = slot.textContent;
        summaryTime.textContent = selectedTime;
      });
    });

    styleSelect.addEventListener("change", () => {
      summaryStyle.textContent = styleSelect.value || "Сонгогдоогүй";
    });

    dateInput.addEventListener("change", () => {
      summaryDate.textContent = dateInput.value || "Сонгогдоогүй";
    });

    function bookAppointment() {
      const name = document.getElementById("name").value.trim();
      const phone = document.getElementById("phone").value.trim();
      const style = styleSelect.value;
      const date = dateInput.value;
      const successMessage = document.getElementById("successMessage");

      if (!selectedArtist) {
        alert("Та эхлээд артистaa сонгоно уу.");
        return;
      }

      if (!name || !phone || !style || !date || !selectedTime) {
        alert("Та бүх шаардлагатай мэдээллийг бүрэн бөглөнө үү.");
        return;
      }

      successMessage.style.display = "block";

      setTimeout(() => {
        successMessage.style.display = "none";
      }, 4000);
    }
  </script>

</body>
</html>
