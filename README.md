<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>تواصل معنا | سهل العمارة</title>
  <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700;800&display=swap" rel="stylesheet" />
  <style>
    :root {
      --primary-color: #2c3e50; /* أزرق داكن أنيق */
      --secondary-color: #e67e22; /* برتقالي حيوي */
      --accent-color: #1abc9c; /* أخضر زمردي */
      --text-dark: #34495e; /* رمادي داكن للنصوص */
      --text-light: #7f8c8d; /* رمادي فاتح للنصوص الثانوية */
      --background: #ecf0f1; /* خلفية رمادية فاتحة جداً */
      --surface-color: #ffffff; /* لون الأسطح مثل الكروت */
      --border-color: #dde1e2; /* لون الحدود */
      --shadow-md: 0 6px 15px rgba(0,0,0,0.1); /* ظل أكثر نعومة */
      --transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1); /* انتقال انسيابي */
    }
    * {
      margin: 0; padding: 0; box-sizing: border-box;
    }
    body {
      font-family: 'Tajawal', sans-serif;
      background: var(--background);
      color: var(--text-dark);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      line-height: 1.7; /* تحسين قابلية القراءة */
    }
    header, footer {
      background: var(--primary-color);
      color: var(--surface-color); /* استخدام لون السطح الأبيض للنص هنا */
      padding: 25px 30px; /* زيادة الحشوة قليلاً */
      text-align: center;
      box-shadow: var(--shadow-md);
      flex-shrink: 0;
    }
    header h1, footer p {
      margin: 0;
      font-weight: 700;
      font-size: 1.9rem; /* تكبير الخط قليلاً */
    }
    main {
      max-width: 1000px;
      width: 90%; /* إضافة عرض لضمان عدم الامتداد الكامل على الشاشات الكبيرة جداً */
      margin: 50px auto; /* زيادة الهامش العلوي والسفلي */
      background: var(--surface-color); /* استخدام متغير لون السطح */
      padding: 45px 40px; /* زيادة الحشوة */
      border-radius: 20px; /* زيادة استدارة الحواف */
      box-shadow: var(--shadow-md);
      flex-grow: 1;
      animation: fadeInUp 1s var(--transition) forwards;
      opacity: 0;
      transform: translateY(25px);
    }
    h2 {
      text-align: center;
      color: var(--primary-color);
      margin-bottom: 40px; /* زيادة الهامش السفلي */
      font-weight: 800;
      font-size: 2.8rem; /* تكبير الخط */
      letter-spacing: 1.5px; /* زيادة تباعد الأحرف */
    }
    form {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 25px 35px; /* زيادة الفجوات */
      margin-bottom: 45px; /* زيادة الهامش السفلي */
    }
    form textarea {
      grid-column: span 2;
      resize: vertical;
      min-height: 130px; /* زيادة الحد الأدنى للارتفاع */
    }
    input, textarea {
      padding: 16px 20px; /* زيادة الحشوة */
      border: 2px solid var(--border-color); /* استخدام متغير لون الحدود */
      border-radius: 15px; /* زيادة استدارة الحواف */
      font-size: 1.15rem; /* تكبير الخط قليلاً */
      font-family: 'Tajawal', sans-serif;
      transition: border-color 0.3s ease, box-shadow 0.3s ease; /* إضافة انتقال للظل */
      outline-offset: 3px; /* زيادة الإزاحة */
      background-color: var(--background); /* خلفية خفيفة للحقول */
      color: var(--text-dark);
    }
    input:focus, textarea:focus {
      border-color: var(--primary-color);
      outline: none;
      box-shadow: 0 0 0 4px rgba(44, 62, 80, 0.1); /* تغيير ظل التركيز ليتناسب مع اللون الأساسي */
    }
    /* أنماط للتحقق من صحة النموذج */
    input:invalid, textarea:invalid {
      border-color: #e74c3c; /* لون أحمر للخطأ */
    }
    .form-submitted input:invalid,
    .form-submitted textarea:invalid {
      border-color: #e74c3c;
      box-shadow: 0 0 0 4px rgba(231, 76, 60, 0.1);
    }
    input:valid, textarea:valid {
      border-color: var(--accent-color); /* لون أخضر للصحة */
    }
    .form-submitted input:valid,
    .form-submitted textarea:valid {
        border-color: var(--accent-color);
        box-shadow: 0 0 0 4px rgba(26, 188, 156, 0.1);
    }

    button {
      grid-column: span 2;
      background: var(--primary-color);
      color: var(--surface-color); /* استخدام لون السطح الأبيض للنص هنا */
      padding: 18px 0; /* زيادة الحشوة */
      border: none;
      border-radius: 35px; /* زيادة استدارة الحواف */
      font-size: 1.3rem; /* تكبير الخط */
      font-weight: 700;
      cursor: pointer;
      transition: background 0.3s ease, transform 0.2s ease, box-shadow 0.3s ease; /* إضافة انتقال للظل */
      box-shadow: var(--shadow-md);
      text-transform: uppercase; /* جعل النص بأحرف كبيرة */
      letter-spacing: 1px; /* إضافة تباعد أحرف طفيف */
    }
    button:hover {
      background: var(--secondary-color);
      transform: translateY(-4px) scale(1.02); /* تأثير رفع وتكبير طفيف */
      box-shadow: 0 10px 25px rgba(230, 126, 34, 0.4); /* ظل أعمق يتناسب مع اللون الثانوي */
    }
    .contact-info {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 30px; /* زيادة الفجوة */
      font-size: 1.2rem; /* تكبير الخط */
      color: var(--text-light);
    }
    .contact-item {
      flex: 1 1 230px; /* تعديل المرونة والقاعدة */
      display: flex;
      align-items: center;
      gap: 18px; /* زيادة الفجوة */
      background: var(--surface-color); /* استخدام لون السطح */
      padding: 18px 22px; /* زيادة الحشوة */
      border-radius: 15px; /* زيادة استدارة الحواف */
      box-shadow: 0 3px 10px rgba(0,0,0,0.07); /* ظل خفيف */
      transition: background 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease;
      border: 1px solid var(--border-color); /* إضافة حد خفيف */
    }
    .contact-item:hover {
      background: var(--primary-color); /* تغيير الخلفية عند التمرير للون الأساسي */
      color: var(--surface-color); /* تغيير لون النص ليتناسب */
      transform: translateY(-5px);
      box-shadow: 0 8px 15px rgba(44, 62, 80, 0.15);
    }
    .contact-item:hover .icon-container svg, .contact-item:hover a {
      color: var(--surface-color) !important; /* ضمان تغيير لون الأيقونة والرابط */
    }
    .contact-item .icon-container {
      color: var(--primary-color);
      min-width: 35px; /* زيادة الحد الأدنى للعرض */
      text-align: center;
      transition: color 0.3s ease;
      display: inline-flex; /* لتمكين التحكم في حجم SVG بشكل أفضل */
      align-items: center;
      justify-content: center;
    }
    .contact-item .icon-container svg {
      width: 2rem; /* تكبير الأيقونات */
      height: 2rem; /* تكبير الأيقونات */
      stroke-width: 1.5; /* سمك خط الأيقونة */
    }
    .contact-item a {
      color: var(--text-dark);
      text-decoration: none;
      font-weight: 600;
      transition: color 0.3s ease;
    }
    .contact-item a:hover {
      color: var(--secondary-color); /* تغيير لون الرابط عند التمرير للون الثانوي */
      text-decoration: underline;
    }
    /* خريطة جوجل */
    .map-container {
      margin-top: 50px; /* زيادة الهامش العلوي */
      border-radius: 20px; /* زيادة استدارة الحواف */
      overflow: hidden;
      box-shadow: var(--shadow-md);
      height: 380px; /* زيادة الارتفاع قليلاً */
    }
    iframe {
      width: 100%;
      height: 100%;
      border: none;
    }
    /* رسالة تأكيد */
    .success-message {
      display: none;
      text-align: center;
      padding: 18px 22px; /* زيادة الحشوة */
      margin-bottom: 35px; /* زيادة الهامش السفلي */
      background: var(--accent-color);
      color: var(--surface-color); /* استخدام لون السطح الأبيض للنص هنا */
      font-weight: 700;
      border-radius: 15px; /* زيادة استدارة الحواف */
      font-size: 1.15rem; /* تكبير الخط قليلاً */
      animation: fadeInDown 0.6s var(--transition) forwards;
      box-shadow: 0 4px 10px rgba(26, 188, 156, 0.3); /* إضافة ظل للرسالة */
    }
    /* أنيميشن */
    @keyframes fadeInUp {
      from { /* إضافة from ليكون التعريف كاملاً */
        opacity: 0;
        transform: translateY(25px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    @keyframes fadeInDown {
      from {
        opacity: 0;
        transform: translateY(-20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    .contact-item {
      /* ... الأنماط الحالية ... */
      opacity: 0; /* إخفاء العناصر مبدئيًا */
      animation: fadeInUp 0.8s var(--transition) forwards; /* تطبيق الأنيميشن */
    }
    .contact-item:nth-child(1) {
      animation-delay: 0.2s;
    }
    .contact-item:nth-child(2) {
      animation-delay: 0.4s;
    }
    .contact-item:nth-child(3) {
      animation-delay: 0.6s;
    }
    .contact-item:nth-child(4) {
      animation-delay: 0.8s;
    }

    /* استجابة الموبايل */
    @media (max-width: 768px) {
      form {
        grid-template-columns: 1fr;
      }
      button {
        grid-column: span 1;
      }
      .contact-info {
        flex-direction: column;
      }
      .contact-item {
        flex: 1 1 100%;
      }
      main {
        margin: 20px 15px;
        padding: 30px 20px;
      }
    }
  </style>
</head>
<body>

<header>
  <h1>سهل العمارة للمقاولات</h1>
</header>

<main>
  <h2>تواصل معنا</h2>
  <div class="success-message" id="successMessage">تم إرسال رسالتك بنجاح، شكرًا لتواصلك معنا!</div>
  <form id="contactForm" novalidate>
    <input type="text" name="name" placeholder="الاسم الكامل" required aria-label="الاسم الكامل" />
    <input type="email" name="email" placeholder="البريد الإلكتروني" required aria-label="البريد الإلكتروني" />
    <div>
      <input type="tel" name="phone" placeholder="رقم الهاتف" required pattern="[0-9+]{8,15}" aria-describedby="phoneHelp" aria-label="رقم الهاتف" />
      <small id="phoneHelp" style="font-size: 0.85em; color: var(--text-light); margin-top: 4px; display: block;">مثال: +9665XXXXXXXX أو 05XXXXXXXX (8-15 رقمًا)</small>
    </div>
    <div></div> <!-- عنصر فارغ لموازنة الشبكة إذا كان الهاتف يأخذ عمودًا واحدًا -->
    <textarea name="message" rows="5" placeholder="اكتب رسالتك هنا..." required aria-label="اكتب رسالتك هنا"></textarea>
    <button type="submit">إرسال الرسالة</button>
  </form>

  <div class="contact-info">
    <div class="contact-item">
      <span class="icon-container">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
          <path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z" />
          <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z" />
        </svg>
      </span>
      الرياض، حي الورود، السعودية
    </div>
    <div class="contact-item">
      <span class="icon-container">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
          <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 01-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 6.75z" />
        </svg>
      </span>
      <a href="tel:0546369829">0546369829</a>
    </div>
    <div class="contact-item">
      <span class="icon-container">
        <!-- أيقونة واتساب SVG مخصصة أو أيقونة رسالة عامة -->
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
          <path stroke-linecap="round" stroke-linejoin="round" d="M8.625 12a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0H8.25m4.125 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0H12m4.125 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0h-.375M21 12c0 4.556-3.86 8.25-8.625 8.25S3.75 16.556 3.75 12D3.75 7.444 7.61 3.75 12.375 3.75S21 7.444 21 12z" />
        </svg>
      </span>
      <a href="https://wa.me/966546369829" target="_blank" rel="noopener">واتساب مباشر</a>
    </div>
    <div class="contact-item">
      <span class="icon-container">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
          <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75" />
        </svg>
      </span>
      <a href="mailto:sahlalemara11@gmail.com">sahlalemara11@gmail.com</a>
    </div>
  </div>

  <div class="map-container" aria-label="خريطة موقع سهل العمارة">
    <iframe 
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3624.1234567890123!2d46.715!3d24.7136!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3e2f03e9f3d7f1f5%3A0x123456789abcdef!2z2KfZhNi52KfZhNmH2YjYp9mE2KfYqNmK2Kkg2KfZhNiq2YjYr9mK2YQg2YjYp9mE2KfYqNin2YTYr9mB2KfYtdmK2Kkg2KfZhNmK2Kkg2YXYr9mK2Kkg2YjYp9mE2YbYqQ!5e0!3m2!1sar!2ssa!4v1687670000000!5m2!1sar!2ssa" 
      allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"
      title="خريطة موقع سهل العمارة"></iframe>
  </div>
</main>

<footer>
  <p>جميع الحقوق محفوظة &copy; 2025 سهل العمارة للمقاولات</p>
</footer>

<script>
  const form = document.getElementById('contactForm');
  const successMessage = document.getElementById('successMessage');

  form.addEventListener('submit', e => {
    e.preventDefault();
    form.classList.add('form-submitted'); // إضافة الفئة عند محاولة الإرسال

    // تحقق من صحة النموذج (يمكن إضافة تحقق أعمق هنا)
    if (!form.checkValidity()) {
      // form.reportValidity(); // يمكن إزالة هذا إذا كانت الأنماط كافية
      // إيجاد أول حقل غير صالح والتركيز عليه لتحسين تجربة المستخدم
      const firstInvalidField = form.querySelector(':invalid');
      if (firstInvalidField) {
        firstInvalidField.focus();
      }
      return;
    }

    // هنا يمكنك إضافة كود إرسال البيانات إلى سيرفر أو API
    // مثلاً: fetch أو XMLHttpRequest
    console.log('تم إرسال النموذج بنجاح (محاكاة)');

    // عرض رسالة النجاح مع أنيميشن
    successMessage.style.display = 'block';
    successMessage.setAttribute('aria-live', 'assertive'); // لإعلام قارئات الشاشة

    // إخفاء الرسالة بعد 5 ثواني وإزالة فئة الإرسال
    setTimeout(() => {
      successMessage.style.display = 'none';
      successMessage.removeAttribute('aria-live');
      form.classList.remove('form-submitted'); // إزالة الفئة بعد النجاح
      // إعادة تعيين ألوان الحدود للحقول إلى الوضع الافتراضي
      form.querySelectorAll('input, textarea').forEach(field => {
        field.style.borderColor = ''; // يزيل اللون الخاص بالصحة/الخطأ
        field.style.boxShadow = ''; // يزيل الظل الخاص بالصحة/الخطأ
      });
    }, 5000);

    form.reset();
    // بعد إعادة التعيين، قد تحتاج إلى إزالة فئة form-submitted مرة أخرى
    // أو التأكد من أن الحقول لا تظهر كـ valid/invalid مباشرة
    // الطريقة الأبسط هي عدم إزالة form-submitted إلا بعد النجاح
  });

  // اختياري: إزالة ألوان الحدود عند البدء في الكتابة مجددًا في حقل كان غير صالح
  form.querySelectorAll('input, textarea').forEach(field => {
    field.addEventListener('input', () => {
      if (form.classList.contains('form-submitted')) {
        // إذا كان الحقل صالحًا الآن، سيتم تطبيق نمط :valid
        // إذا كان لا يزال غير صالح، سيبقى نمط :invalid
        // لا نحتاج لإجراء معين هنا بالضرورة مع الأنماط الحالية
      }
    });
  });
</script>

</body>
</html>

تواصل معنا
