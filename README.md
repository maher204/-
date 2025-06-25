<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>تواصل معنا | سهل العمارة</title>
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" />
  <style>
    :root {
      --primary-color: #4F46E5;
      --secondary-color: #F59E0B;
      --accent-color: #10B981;
      --text-dark: #1F2937;
      --text-light: #6B7280;
      --background: #f9fafb;
      --shadow-md: 0 4px 12px rgba(0,0,0,0.08);
      --transition: all 0.3s ease;
    }
    * {
      margin: 0; padding: 0; box-sizing: border-box;
    }
    body {
      font-family: 'Cairo', sans-serif;
      background: var(--background);
      color: var(--text-dark);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }
    header, footer {
      background: var(--primary-color);
      color: white;
      padding: 20px 30px;
      text-align: center;
      box-shadow: var(--shadow-md);
      flex-shrink: 0;
    }
    header h1, footer p {
      margin: 0;
      font-weight: 700;
      font-size: 1.8rem;
    }
    main {
      max-width: 1000px;
      margin: 40px auto;
      background: white;
      padding: 40px 35px;
      border-radius: 15px;
      box-shadow: var(--shadow-md);
      flex-grow: 1;
      animation: fadeInUp 1s ease forwards;
      opacity: 0;
      transform: translateY(20px);
    }
    h2 {
      text-align: center;
      color: var(--primary-color);
      margin-bottom: 35px;
      font-weight: 800;
      font-size: 2.5rem;
      letter-spacing: 1.2px;
    }
    form {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px 30px;
      margin-bottom: 40px;
    }
    form textarea {
      grid-column: span 2;
      resize: vertical;
      min-height: 120px;
    }
    input, textarea {
      padding: 14px 18px;
      border: 2px solid #ddd;
      border-radius: 12px;
      font-size: 1.1rem;
      font-family: 'Cairo', sans-serif;
      transition: border-color 0.3s ease;
      outline-offset: 2px;
    }
    input:focus, textarea:focus {
      border-color: var(--primary-color);
      outline: none;
      box-shadow: 0 0 8px rgba(79, 70, 229, 0.4);
    }
    button {
      grid-column: span 2;
      background: var(--primary-color);
      color: white;
      padding: 16px 0;
      border: none;
      border-radius: 30px;
      font-size: 1.25rem;
      font-weight: 700;
      cursor: pointer;
      transition: background 0.3s ease, transform 0.2s ease;
      box-shadow: var(--shadow-md);
    }
    button:hover {
      background: var(--secondary-color);
      transform: translateY(-3px);
      box-shadow: 0 8px 20px rgba(245, 158, 11, 0.5);
    }
    .contact-info {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 25px;
      font-size: 1.15rem;
      color: var(--text-light);
    }
    .contact-item {
      flex: 1 1 220px;
      display: flex;
      align-items: center;
      gap: 15px;
      background: #f0f4ff;
      padding: 15px 20px;
      border-radius: 12px;
      box-shadow: 0 2px 8px rgba(79, 70, 229, 0.1);
      transition: background 0.3s ease;
    }
    .contact-item:hover {
      background: #e0e7ff;
    }
    .contact-item i {
      color: var(--primary-color);
      font-size: 1.8rem;
      min-width: 30px;
      text-align: center;
    }
    .contact-item a {
      color: var(--text-dark);
      text-decoration: none;
      font-weight: 600;
      transition: color 0.3s ease;
    }
    .contact-item a:hover {
      color: var(--primary-color);
      text-decoration: underline;
    }
    /* خريطة جوجل */
    .map-container {
      margin-top: 45px;
      border-radius: 15px;
      overflow: hidden;
      box-shadow: var(--shadow-md);
      height: 350px;
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
      padding: 15px 20px;
      margin-bottom: 30px;
      background: var(--accent-color);
      color: white;
      font-weight: 700;
      border-radius: 12px;
      font-size: 1.1rem;
      animation: fadeInDown 0.6s ease forwards;
    }
    /* أنيميشن */
    @keyframes fadeInUp {
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
    <input type="text" name="name" placeholder="الاسم الكامل" required />
    <input type="email" name="email" placeholder="البريد الإلكتروني" required />
    <input type="tel" name="phone" placeholder="رقم الهاتف" required pattern="[0-9+]{8,15}" />
    <textarea name="message" rows="5" placeholder="اكتب رسالتك هنا..." required></textarea>
    <button type="submit">إرسال الرسالة</button>
  </form>

  <div class="contact-info">
    <div class="contact-item"><i class="fas fa-map-marker-alt"></i> الرياض، حي الورود، السعودية</div>
    <div class="contact-item"><i class="fas fa-phone-alt"></i> <a href="tel:0546369829">0546369829</a></div>
    <div class="contact-item"><i class="fab fa-whatsapp"></i> <a href="https://wa.me/966546369829" target="_blank" rel="noopener">واتساب مباشر</a></div>
    <div class="contact-item"><i class="fas fa-envelope"></i> <a href="mailto:sahlalemara11@gmail.com">sahlalemara11@gmail.com</a></div>
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

    // تحقق من صحة النموذج (يمكن إضافة تحقق أعمق هنا)
    if (!form.checkValidity()) {
      form.reportValidity();
      return;
    }

    // هنا يمكنك إضافة كود إرسال البيانات إلى سيرفر أو API
    // مثلاً: fetch أو XMLHttpRequest

    // عرض رسالة النجاح مع أنيميشن
    successMessage.style.display = 'block';

    // إخفاء الرسالة بعد 5 ثواني
    setTimeout(() => {
      successMessage.style.display = 'none';
    }, 5000);

    form.reset();
  });
</script>

</body>
</html>

تواصل معنا
