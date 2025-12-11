#Reservation d'holel�
<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>نظام الحجز الفندقي</title>
  
  <!-- ربط بأيقونات Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

  <style>
    /* إعدادات عامة للصفحة */
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      padding: 0;
      direction: rtl; /* لجعل اتجاه النص من اليمين لليسار */
      background: linear-gradient(to right, #5fb7ff, #373e7c); /* خلفية متدرجة */
    }

    /* قسم المقدمة */
    .hero {
      background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), 
                  url('https://images.unsplash.com/photo-1600585154340-be6161a56a0c') center/cover no-repeat;
      height: 90vh;
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      animation: fadeIn 2s ease-in; /* تأثير ظهور */
    }

    .hero h1 {
      font-size: 50px;
      margin-bottom: 20px;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
    }

    .hero p {
      font-size: 20px;
      max-width: 700px;
      margin: 0 auto;
    }

    /* حركة الظهور */
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* رأس الصفحة */
    header {
      background-color: #1e3c5cfd;
      padding: 15px 30px;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-wrap: wrap;
      position: sticky;
      top: 0;
      z-index: 1000; /* ليبقى في الأعلى أثناء التمرير */
    }

    header h1 {
      font-size: 24px;
      margin: 0 20px;
      font-weight: bold;
    }

    nav {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-wrap: wrap;
    }

    nav a {
      color: #57ffe3fa;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
      font-size: 18px;
      transition: color 0.3s;
    }

    nav a:hover {
      color: #ffffff;
      text-decoration: underline;
    }

    section {
      padding: 60px 20px;
      margin-bottom: 20px;
    }

    /* عنوان القسم */
    .section-title {
      font-size: 32px;
      text-align: center;
      margin-bottom: 30px;
      color: #16212c;
      position: relative;
    }

    .section-title::after {
      content: '';
      width: 80px;
      height: 4px;
      background: #d30a0a;
      display: block;
      margin: 10px auto 0;
      border-radius: 2px;
    }

    /* مربعات الإدخال */
    .box {
      background-color: #ffffff;
      padding: 25px;
      margin: auto;
      border-radius: 12px;
      max-width: 700px;
      box-shadow: 0 4px 25px rgba(0,0,0,0.1);
      background: linear-gradient(to right, #f8f9fa, #e9ecef);
    }

    label {
      display: block;
      margin-top: 15px;
      font-size: 16px;
      color: #021c35;
    }

    input[type="text"], input[type="number"], input[type="date"] {
      width: 96%;
      padding: 12px;
      margin-top: 5px;
      font-size: 16px;
      border: 1px solid #c55d5d;
      border-radius: 6px;
    }

    /* زر الإرسال */
    button {
      margin-top: 20px;
      padding: 12px 25px;
      background-color: #24e412;
      border: none;
      color: white;
      font-size: 16px;
      border-radius: 6px;
      cursor: pointer;
      transition: background 0.3s;
    }

    button:hover {
      background-color: #e98f4a;
    }

    /* نتيجة التسجيل أو البحث */
    .result {
      margin-top: 20px;
      background: #f1f8ff;
      padding: 12px;
      border-radius: 6px;
      font-size: 16px;
      color: #406a94;
    }

    /* بطاقات العروض */
    .offers {
      display: flex;
      gap: 30px;
      flex-wrap: wrap;
      justify-content: center;
    }

    .offer-card {
      background: linear-gradient(135deg, #ffffff, #f0f0f0);
      border: 1px solid #dcdde1;
      padding: 20px;
      width: 260px;
      border-radius: 12px;
      text-align: center;
      transition: transform 0.3s ease;
      box-shadow: 0 3px 15px rgba(0,0,0,0.1);
    }

    .offer-card:hover {
      transform: scale(1.05);
      background: #7d8aff;
    }

    /* صندوق الأسعار */
    .price-box {
      background-color: #f9f9f9;
      padding: 15px;
      border-left: 6px solid #0fd8ce;
      margin-bottom: 15px;
      border-radius: 8px;
      font-size: 18px;
      color: #2c3e50;
    }

    /* تنسيق القائمة */
    ul {
      list-style: none;
      padding: 0;
    }

    ul li::before {
      content: "✔️ ";
      color: #27ae60;
    }

    /* تأثير عند المرور على أيقونات التواصل */
    footer a i:hover {
      transform: scale(1.2);
      transition: transform 0.3s;
    }
  </style>
</head>
<body>

  <!-- قسم المقدمة -->
  <div class="hero">
    <div>
      <h1>مرحباً بكم في عالم الراحة والرفاهية</h1>
      <p>نقدم لكم أفضل العروض الفندقية وخدمات الحجز بأسعار تنافسية وراحة لا مثيل لها في أرقى المدن الجزائرية.</p>
    </div>
  </div>

  <!-- رأس الموقع -->
  <header>
    <h1>🌍 نظام الحجز الفندقي</h1>
    <nav>
      <a href="#register">التسجيل</a>
      <a href="#search">بحث العميل</a>
      <a href="#offers">عروض الفنادق</a>
      <a href="#prices">أسعار الغرف</a>
      <a href="#program">برنامج الحجز</a>
      <a href="#reservation">حجز غرفة</a>
      <a href="#rating">تقييم الفندق</a>
    </nav>
    
  </header>

  <!-- قسم تسجيل عميل جديد -->
  <section id="register">
    <h2 class="section-title"> تسجيل عميل جديد</h2>
    <div class="box">
      <form id="registerForm" onsubmit="registerClient(event)">
        <label for="nom">الاسم:</label>
        <input type="text" id="nom" required>

        <label for="prenom">اللقب:</label>
        <input type="text" id="prenom" required>

        <button type="submit">تسجيل</button>
      </form>
      <div id="registerMsg" class="result"></div>
    </div>
  </section>

  <!-- قسم البحث عن عميل -->
  <section id="search">
    <h2 class="section-title"> البحث عن عميل</h2>
    <div class="box">
      <label for="searchName">ادخل اسم العميل:</label>
      <input type="text" id="searchName" placeholder="مثال: سامي">
      <button onclick="searchClient()">بحث</button>
      <div id="searchResult" class="result"></div>
    </div>
  </section>

  <!-- قسم عروض الفنادق -->
  <section id="offers">
    <h2 class="section-title"> عروض الفنادق</h2>
    <div class="offers">
      <div class="offer-card">
        <h3>باقة شهر العسل</h3>
        <p>3 ليالٍ + وجبات + خصم %20</p>
        <strong>السعر: 45,000 دج</strong>
      </div>
      <div class="offer-card">
        <h3>عرض الصيف</h3>
        <p>7 ليالٍ بسعر 5 فقط</p>
        <strong>السعر: 70,000 دج</strong>
      </div>
      <div class="offer-card">
        <h3>عرض نهاية الأسبوع</h3>
        <p>ليلتين + تذكرة عرض مجانية</p>
        <strong>السعر: 18,000 دج</strong>
      </div>
    </div>
  </section>

  <!-- قسم الأسعار -->
  <section id="prices">
    <h2 class="section-title"> أسعار الغرف</h2>
    <div class="box">
      <div class="price-box"><strong>Standard:</strong> 5,000 دج/ليلة</div>
      <div class="price-box"><strong>Deluxe:</strong> 8,000 دج/ليلة</div>
      <div class="price-box"><strong>Suite:</strong> 12,000 دج/ليلة</div>
    </div>
  </section>

  <!-- قسم برنامج الحجز -->
  <section id="program">
    <h2 class="section-title"> برنامج الحجز</h2>
    <div class="box">
      <p> إختر العرض المناسب وقم بالحجز عبر التواصل معنا:</p>
      <ul>
        <li> 0555-123456</li>
        <li> hotel@booking.dz</li>
        <li> يوميًا من 8 صباحًا حتى 10 مساءً</li>
      </ul>
    </div>
  </section>
<!-- قسم حجز الغرفة -->
<section id="reservation">
  <h2 class="section-title"> حجز غرفة</h2>
  <div class="box">
    <form id="reservationForm" onsubmit="reserveRoom(event)">
      <label for="clientName">اسم العميل:</label>
      <input type="text" id="clientName" required>

      <label for="roomType">نوع الغرفة:</label>
      <select id="roomType" required>
        <option value="Standard">Standard</option>
        <option value="Deluxe">Deluxe</option>
        <option value="Suite">Suite</option>
      </select>

      <label for="nights">عدد الليالي:</label>
      <input type="number" id="nights" min="1" required>

      <label for="date">تاريخ الوصول:</label>
      <input type="date" id="date" required>

      <button type="submit">حجز</button>
    </form>
    <div id="reservationMsg" class="result"></div>
  </div>
</section>

<!-- قسم تقييم الفندق -->
<section id="rating">
  <h2 class="section-title"> تقييم الفندق</h2>
  <div class="box">
    <form id="ratingForm" onsubmit="submitRating(event)">
      <label for="ratingStars">عدد النجوم:</label>
      <select id="ratingStars" required>
        <option value="">اختر التقييم</option>
        <option value="1">⭐</option>
        <option value="2">⭐⭐</option>
        <option value="3">⭐⭐⭐</option>
        <option value="4">⭐⭐⭐⭐</option>
        <option value="5">⭐⭐⭐⭐⭐</option>
      </select>

      <label for="comment">تعليق:</label>
      <input type="text" id="comment" placeholder="اكتب تعليقك هنا..." required>

      <button type="submit">إرسال التقييم</button>
    </form>
    <div id="ratingMsg" class="result"></div>
  </div>
</section>

  <!-- التذييل -->
  <footer style="background-color: #1e3c5c; color: white; text-align: center; padding: 25px; margin-top: 40px;">
    <p>&copy; 2025 نظام الحجز الفندقي. جميع الحقوق محفوظة.</p>

    <p>
      <a href="contact.html" style="color: #87fff5; margin: 0 10px; text-decoration: none;">اتصل بنا</a> |
      <a href="about.html" style="color: #87fff5; margin: 0 10px; text-decoration: none;">عن النظام</a> |
      <a href="https://hotel-booking.dz/privacy" target="_blank" rel="noopener noreferrer" style="color: #87fff5; margin: 0 10px; text-decoration: none;">سياسة الخصوصية</a>
    </p>

    <!-- أيقونات تواصل اجتماعي -->
    <div style="margin-top: 15px;">
      <a href="https://facebook.com/YourHotelPage" target="_blank" style="color: #fff; margin: 0 10px; font-size: 20px;">
        <i class="fab fa-facebook-f"></i>
      </a>
      <a href="https://instagram.com/YourHotelPage" target="_blank" style="color: #fff; margin: 0 10px; font-size: 20px;">
        <i class="fab fa-instagram"></i>
      </a>
      <a href="https://twitter.com/YourHotelPage" target="_blank" style="color: #fff; margin: 0 10px; font-size: 20px;">
        <i class="fab fa-twitter"></i>
      </a>
    </div>
  </footer>

  <!-- زر للعودة لأعلى الصفحة -->
  <div style="margin-top: 20px;">
    <button onclick="window.scrollTo({ top: 0, behavior: 'smooth' });"
      style="background-color: #3aa8d3; color: #09121d; padding: 10px 20px; border: none; border-radius: 5px; cursor: pointer;">
      🔝 العودة لأعلى
    </button>
  </div>

  <!-- جافاسكربت -->
  <script>
    // مصفوفة لتخزين بيانات العملاء
    const clients = [];

    // دالة لتسجيل عميل جديد
    function registerClient(e) {
      e.preventDefault();
      const nom = document.getElementById("nom").value.trim();
      const prenom = document.getElementById("prenom").value.trim();
      const msg = document.getElementById("registerMsg");

      if (nom && prenom) {
        clients.push({ nom, prenom }); // إضافة العميل إلى القائمة
        msg.innerHTML = `✅ تم تسجيل العميل: <strong>${nom} ${prenom}</strong>`;
        e.target.reset(); // إعادة تعيين النموذج
      } else {
        msg.innerHTML = " يرجى ملء جميع الحقول.";
      }
    }

    // دالة للبحث عن العملاء بالاسم
    function searchClient() {
      const name = document.getElementById("searchName").value.trim().toLowerCase();
      const result = document.getElementById("searchResult");

      if (!name) {
        result.innerHTML = " يرجى إدخال اسم للبحث.";
        return;
      }

      // فلترة العملاء حسب الاسم المدخل
      const matches = clients.filter(c => c.nom.toLowerCase().includes(name));

      if (matches.length > 0) {
        result.innerHTML = "<strong>العملاء المطابقون:</strong><ul>" +
          matches.map(c => `<li>${c.nom} ${c.prenom}</li>`).join("") + "</ul>";
      } else {
        result.innerHTML = "❌ لا يوجد عميل بهذا الاسم.";
      }
    }
    // دالة لحجز غرفة
function reserveRoom(e) {
  e.preventDefault();
  const name = document.getElementById("clientName").value.trim();
  const type = document.getElementById("roomType").value;
  const nights = document.getElementById("nights").value;
  const date = document.getElementById("date").value;
  const msg = document.getElementById("reservationMsg");

  if (name && type && nights && date) {
    msg.innerHTML = `✅ تم حجز غرفة <strong>${type}</strong> لـ <strong>${name}</strong> لمدة <strong>${nights}</strong> ليلة ابتداءً من <strong>${date}</strong>.`;
    e.target.reset();
  } else {
    msg.innerHTML = "❌ يرجى ملء جميع الحقول.";
  }
}

// دالة لتقييم الفندق
function submitRating(e) {
  e.preventDefault();
  const stars = document.getElementById("ratingStars").value;
  const comment = document.getElementById("comment").value.trim();
  const msg = document.getElementById("ratingMsg");

  if (stars && comment) {
    msg.innerHTML = `🌟 تم إرسال تقييمك: <strong>${stars} نجوم</strong><br>💬 التعليق: "${comment}"`;
    e.target.reset();
  } else {
    msg.innerHTML = "❌ يرجى تحديد عدد النجوم وكتابة تعليق.";
  }
}

  </script>

</body>
</html>





