<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mammy Kitchen | Barmeshwar Maniya Startup</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    :root {
      --brand: #d62828;
      --brand-dark: #9d0208;
      --accent: #fcbf49;
      --bg: #fff8f0;
      --text: #222;
      --card: #ffffff;
      --muted: #666;
      --green: #1f9d55;
      --shadow: 0 10px 30px rgba(0,0,0,0.12);
    }
    body {
      font-family: Arial, Helvetica, sans-serif;
      background: linear-gradient(180deg, #fff8f0, #fffdf8);
      color: var(--text);
      line-height: 1.6;
    }
    html { scroll-behavior: smooth; }
    a { text-decoration: none; }
    .container { width: min(1200px, 92%); margin: auto; }
    .btn {
      display: inline-block;
      padding: 12px 20px;
      border-radius: 999px;
      font-weight: 700;
      transition: .25s ease;
      cursor: pointer;
      border: none;
    }
    .btn-primary {
      background: var(--brand);
      color: #fff;
      box-shadow: var(--shadow);
    }
    .btn-primary:hover { background: var(--brand-dark); transform: translateY(-2px); }
    .btn-secondary {
      background: #fff;
      color: var(--brand);
      border: 2px solid var(--brand);
    }
    .btn-secondary:hover { background: #fff1f1; }
    .section-title {
      text-align: center;
      font-size: 2rem;
      margin-bottom: 10px;
      color: var(--brand-dark);
    }
    .section-sub {
      text-align: center;
      color: var(--muted);
      margin-bottom: 30px;
    }

    /* Navbar */
    header {
      position: sticky;
      top: 0;
      z-index: 999;
      background: rgba(255,255,255,0.96);
      backdrop-filter: blur(8px);
      box-shadow: 0 2px 10px rgba(0,0,0,0.06);
    }
    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 14px 0;
      gap: 16px;
      flex-wrap: wrap;
    }
    .logo {
      font-size: 1.5rem;
      font-weight: 800;
      color: var(--brand-dark);
    }
    .logo span { color: var(--brand); }
    .nav-links {
      display: flex;
      gap: 18px;
      flex-wrap: wrap;
      align-items: center;
    }
    .nav-links a {
      color: var(--text);
      font-weight: 600;
      font-size: 0.95rem;
    }
    .nav-links a:hover { color: var(--brand); }

    /* Hero */
    .hero {
      padding: 70px 0 40px;
      background: radial-gradient(circle at top right, #ffe5d9 0%, #fff8f0 40%, #fffdf8 100%);
    }
    .hero-wrap {
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      gap: 30px;
      align-items: center;
    }
    .hero h1 {
      font-size: clamp(2rem, 4vw, 4rem);
      line-height: 1.1;
      margin-bottom: 15px;
      color: var(--brand-dark);
    }
    .hero p {
      color: #444;
      margin-bottom: 22px;
      font-size: 1.05rem;
    }
    .hero-badges {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
      margin-bottom: 20px;
    }
    .badge {
      background: #fff;
      padding: 8px 14px;
      border-radius: 999px;
      font-size: 0.9rem;
      box-shadow: 0 4px 14px rgba(0,0,0,0.06);
      font-weight: 700;
      color: var(--brand-dark);
    }
    .hero-actions {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }
    .hero-card {
      background: var(--card);
      border-radius: 24px;
      padding: 22px;
      box-shadow: var(--shadow);
      border: 1px solid #ffe0d6;
    }
    .hero-card h3 { color: var(--brand-dark); margin-bottom: 10px; }
    .mini-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px;
      margin-top: 15px;
    }
    .mini-box {
      background: #fff7f4;
      border-radius: 16px;
      padding: 14px;
      text-align: center;
      border: 1px solid #ffd7c9;
    }
    .mini-box strong { display: block; font-size: 1.1rem; color: var(--brand-dark); }
    .mini-box span { font-size: 0.9rem; color: var(--muted); }

    /* Sections */
    section { padding: 60px 0; }
    .about-box, .payment-box, .contact-box, .review-card, .menu-card, .offer-card, .order-box {
      background: var(--card);
      border-radius: 24px;
      box-shadow: var(--shadow);
      padding: 24px;
    }

    /* About */
    .about-box {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 24px;
      align-items: center;
    }
    .about-list { margin-top: 14px; }
    .about-list li { margin: 8px 0; color: #444; }
    .about-highlight {
      background: #fff7e6;
      border: 1px solid #ffe0a3;
      padding: 16px;
      border-radius: 18px;
      font-weight: 700;
      color: #8a5200;
    }

    /* Menu */
    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
      gap: 20px;
    }
    .menu-card {
      border: 1px solid #ffe3da;
      position: relative;
      overflow: hidden;
    }
    .menu-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 10px;
    }
    .price {
      background: #fff1f1;
      color: var(--brand-dark);
      padding: 6px 12px;
      border-radius: 999px;
      font-weight: 800;
    }
    .menu-card p { color: var(--muted); font-size: 0.95rem; margin-bottom: 14px; }
    .qty-row {
      display: flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 12px;
      flex-wrap: wrap;
    }
    .qty-row input {
      width: 70px;
      padding: 10px;
      border-radius: 10px;
      border: 1px solid #ddd;
      font-weight: 700;
    }

    /* Offers */
    .offer-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
    }
    .offer-card {
      background: linear-gradient(135deg, #fff, #fff5ec);
      border: 1px solid #ffe3b8;
    }
    .offer-card h4 { color: var(--brand-dark); margin-bottom: 8px; }

    /* Order */
    .order-box {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 24px;
    }
    .form-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 14px;
    }
    .full { grid-column: 1 / -1; }
    input, select, textarea {
      width: 100%;
      padding: 13px 14px;
      border: 1px solid #ddd;
      border-radius: 14px;
      font-size: 0.95rem;
      outline: none;
    }
    input:focus, select:focus, textarea:focus {
      border-color: var(--brand);
      box-shadow: 0 0 0 4px rgba(214, 40, 40, 0.08);
    }
    .cart-list {
      background: #fff8f7;
      border-radius: 18px;
      padding: 16px;
      border: 1px solid #ffd9d0;
      min-height: 180px;
    }
    .cart-item {
      display: flex;
      justify-content: space-between;
      gap: 10px;
      padding: 10px 0;
      border-bottom: 1px dashed #e9c5bc;
      font-size: 0.95rem;
    }
    .cart-item:last-child { border-bottom: none; }
    .total-box {
      margin-top: 15px;
      padding: 16px;
      border-radius: 18px;
      background: #fff1f1;
      border: 1px solid #ffd1d1;
      font-weight: 800;
      color: var(--brand-dark);
      font-size: 1.1rem;
    }
    .small-note { font-size: 0.9rem; color: var(--muted); margin-top: 8px; }

    /* Payment */
    .payment-box {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 24px;
      align-items: center;
    }
    .qr-wrap {
      text-align: center;
      background: #f8f9fb;
      border-radius: 24px;
      padding: 18px;
      border: 1px solid #e8ebf0;
    }
    .qr-wrap img {
      width: 100%;
      max-width: 320px;
      border-radius: 18px;
      box-shadow: 0 8px 24px rgba(0,0,0,0.08);
    }
    .upi-card {
      background: #f5fff8;
      border: 1px solid #bfe8cb;
      border-radius: 18px;
      padding: 16px;
      margin-top: 14px;
    }
    .upi-id {
      font-weight: 800;
      color: var(--green);
      word-break: break-all;
    }

    /* Reviews */
    .review-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
    }
    .review-card {
      border: 1px solid #eee;
    }
    .stars { color: #f59e0b; margin-bottom: 10px; }

    /* Contact */
    .contact-box {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }
    .contact-item {
      background: #fff9f7;
      border: 1px solid #ffe2d8;
      border-radius: 18px;
      padding: 18px;
    }
    .contact-item h4 { color: var(--brand-dark); margin-bottom: 8px; }

    /* Footer */
    footer {
      background: #1d1d1d;
      color: #fff;
      padding: 30px 0;
      text-align: center;
      margin-top: 30px;
    }
    .footer-note { color: #cfcfcf; font-size: 0.95rem; margin-top: 6px; }

    /* Floating Buttons */
    .float-wrap {
      position: fixed;
      right: 16px;
      bottom: 16px;
      display: flex;
      flex-direction: column;
      gap: 10px;
      z-index: 999;
    }
    .float-btn {
      width: 56px;
      height: 56px;
      border-radius: 50%;
      display: grid;
      place-items: center;
      color: #fff;
      font-size: 1.4rem;
      box-shadow: var(--shadow);
    }
    .wa { background: #25D366; }
    .pay { background: #2563eb; }

    /* Modal */
    .modal {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.6);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 1000;
      padding: 20px;
    }
    .modal.active { display: flex; }
    .modal-box {
      width: min(560px, 100%);
      background: #fff;
      border-radius: 24px;
      padding: 24px;
      box-shadow: var(--shadow);
      max-height: 90vh;
      overflow: auto;
    }
    .success {
      background: #ecfdf3;
      border: 1px solid #b7ebc6;
      padding: 14px;
      border-radius: 16px;
      color: #0f7a35;
      font-weight: 700;
      margin-top: 14px;
    }

    /* Responsive */
    @media (max-width: 900px) {
      .hero-wrap, .about-box, .order-box, .payment-box, .contact-box {
        grid-template-columns: 1fr;
      }
      .form-grid { grid-template-columns: 1fr; }
    }
    @media (max-width: 600px) {
      .nav { justify-content: center; }
      .nav-links { justify-content: center; }
      .hero { padding-top: 40px; }
      .section-title { font-size: 1.6rem; }
    }
  </style>
</head>
<body>

  <header>
    <div class="container nav">
      <div class="logo">Mammy <span>Kitchen</span></div>
      <nav class="nav-links">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#menu">Menu</a>
        <a href="#order">Order</a>
        <a href="#payment">Payment</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>

  <section class="hero" id="home">
    <div class="container hero-wrap">
      <div>
        <div class="hero-badges">
          <div class="badge">🍱 Institute Delivery</div>
          <div class="badge">💳 Real UPI Payment</div>
          <div class="badge">📱 WhatsApp Order</div>
        </div>
        <h1>Fresh Homemade Food for Students & Campus Life</h1>
        <p>
          Welcome to <strong>Mammy Kitchen</strong> — a student-focused food startup by <strong>Barmeshwar Maniya</strong>.
          Fast, affordable, tasty meals delivered for institute students with easy WhatsApp ordering and real UPI payment support.
        </p>
        <div class="hero-actions">
          <a href="#order" class="btn btn-primary">Order Now</a>
          <a href="https://wa.me/919093252982?text=Hello%20Mammy%20Kitchen%2C%20I%20want%20to%20order%20food." target="_blank" class="btn btn-secondary">WhatsApp Order</a>
        </div>
      </div>
      <div class="hero-card">
        <h3>Today’s Fast Service</h3>
        <p>Specially built for students of Medinipur area institutions with quick lunch ordering.</p>
        <div class="mini-grid">
          <div class="mini-box"><strong>4+</strong><span>Popular Meals</span></div>
          <div class="mini-box"><strong>₹40+</strong><span>Budget Friendly</span></div>
          <div class="mini-box"><strong>UPI</strong><span>Scan & Pay</span></div>
          <div class="mini-box"><strong>Live</strong><span>WhatsApp Support</span></div>
        </div>
      </div>
    </div>
  </section>

  <section id="about">
    <div class="container">
      <h2 class="section-title">About Mammy Kitchen</h2>
      <p class="section-sub">Student startup food service for fast and affordable daily meals</p>
      <div class="about-box">
        <div>
          <p>
            <strong>Mammy Kitchen</strong> is a smart startup idea made by <strong>Barmeshwar Maniya</strong> to help students get tasty,
            hygienic, and low-cost homemade food near campus. This website is designed for easy ordering, fast contact,
            and direct UPI payment.
          </p>
          <ul class="about-list">
            <li>✅ Fresh homemade rice meals</li>
            <li>✅ Perfect for college / polytechnic students</li>
            <li>✅ Direct WhatsApp communication</li>
            <li>✅ Real QR code payment added</li>
            <li>✅ Simple online order request system</li>
          </ul>
        </div>
        <div class="about-highlight">
          Founder: <strong>Barmeshwar Maniya</strong><br>
          WhatsApp: <strong>9093252982</strong><br>
          UPI ID: <strong>barmeshwarmaniya3@oksbi</strong><br>
          Service Type: <strong>Campus Student Food Delivery</strong>
        </div>
      </div>
    </div>
  </section>

  <section id="menu">
    <div class="container">
      <h2 class="section-title">Popular Menu</h2>
      <p class="section-sub">Select quantity and build your order</p>
      <div class="menu-grid">
        <div class="menu-card" data-name="Veg Rice" data-price="40">
          <div class="menu-top"><h3>Veg Rice</h3><span class="price">₹40</span></div>
          <p>Healthy simple veg meal for daily student lunch.</p>
          <div class="qty-row">
            <label>Qty:</label>
            <input type="number" min="0" value="0" class="qty-input">
          </div>
          <button class="btn btn-primary add-btn">Add to Cart</button>
        </div>

        <div class="menu-card" data-name="Egg Rice" data-price="50">
          <div class="menu-top"><h3>Egg Rice</h3><span class="price">₹50</span></div>
          <p>Delicious egg meal for students who want extra protein.</p>
          <div class="qty-row">
            <label>Qty:</label>
            <input type="number" min="0" value="0" class="qty-input">
          </div>
          <button class="btn btn-primary add-btn">Add to Cart</button>
        </div>

        <div class="menu-card" data-name="Fish Rice" data-price="60">
          <div class="menu-top"><h3>Fish Rice</h3><span class="price">₹60</span></div>
          <p>Tasty Bengali-style fish meal at student budget price.</p>
          <div class="qty-row">
            <label>Qty:</label>
            <input type="number" min="0" value="0" class="qty-input">
          </div>
          <button class="btn btn-primary add-btn">Add to Cart</button>
        </div>

        <div class="menu-card" data-name="Chicken Rice" data-price="80">
          <div class="menu-top"><h3>Chicken Rice</h3><span class="price">₹80</span></div>
          <p>Special favorite full meal with tasty chicken curry.</p>
          <div class="qty-row">
            <label>Qty:</label>
            <input type="number" min="0" value="0" class="qty-input">
          </div>
          <button class="btn btn-primary add-btn">Add to Cart</button>
        </div>
      </div>
    </div>
  </section>

  <section>
    <div class="container">
      <h2 class="section-title">Special Offers</h2>
      <p class="section-sub">Best offers for student customers</p>
      <div class="offer-grid">
        <div class="offer-card">
          <h4>🎉 First Order Offer</h4>
          <p>First-time student customers can get a special surprise discount through WhatsApp confirmation.</p>
        </div>
        <div class="offer-card">
          <h4>👨‍🎓 Group Order Benefit</h4>
          <p>Order for friends together from the same institute and get faster delivery coordination.</p>
        </div>
        <div class="offer-card">
          <h4>💥 Daily Campus Meal</h4>
          <p>Affordable daily lunch menu specially designed for hostel and day scholar students.</p>
        </div>
      </div>
    </div>
  </section>

  <section id="order">
    <div class="container">
      <h2 class="section-title">Place Your Order</h2>
      <p class="section-sub">Fill details, review cart, then send order on WhatsApp</p>
      <div class="order-box">
        <div>
          <div class="form-grid">
            <div>
              <label>Full Name</label>
              <input type="text" id="customerName" placeholder="Enter your full name">
            </div>
            <div>
              <label>Mobile Number</label>
              <input type="tel" id="customerPhone" placeholder="Enter mobile number">
            </div>
            <div>
              <label>Email ID</label>
              <input type="email" id="customerEmail" placeholder="Enter email address">
            </div>
            <div>
              <label>Institute Name</label>
              <select id="customerInstitute">
                <option value="">Select institute</option>
                <option>Medinipur Sadar Govt. Polytechnic</option>
                <option>Medinipur City College</option>
                <option>Other Institute</option>
              </select>
            </div>
            <div class="full">
              <label>Delivery Location / Department / Hostel / Room</label>
              <textarea id="customerAddress" rows="4" placeholder="Example: Hostel Gate, Civil Dept, Room 12"></textarea>
            </div>
          </div>
        </div>

        <div>
          <h3 style="margin-bottom:12px;color:#9d0208;">Your Cart</h3>
          <div class="cart-list" id="cartList">
            <p style="color:#666;">No items added yet.</p>
          </div>
          <div class="total-box">Total: ₹<span id="totalAmount">0</span></div>
          <p class="small-note">After payment, click the WhatsApp button below to send order details with total amount.</p>
          <div style="display:flex; gap:10px; flex-wrap:wrap; margin-top:14px;">
            <button class="btn btn-primary" onclick="openPaymentModal()">Proceed to Payment</button>
            <button class="btn btn-secondary" onclick="sendWhatsAppOrder()">Send on WhatsApp</button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="payment">
    <div class="container">
      <h2 class="section-title">Real UPI Payment</h2>
      <p class="section-sub">Scan the QR code or use UPI ID to pay directly</p>
      <div class="payment-box">
        <div class="qr-wrap">
          <img src="my upi.jpeg" alt="Mammy Kitchen UPI QR Code">
          <div class="upi-card">
            <p><strong>UPI ID:</strong></p>
            <p class="upi-id">barmeshwarmaniya3@oksbi</p>
            <p style="margin-top:8px; color:#555;">Scan with any UPI app: PhonePe / Google Pay / Paytm / BHIM</p>
          </div>
        </div>
        <div>
          <div class="about-highlight" style="background:#f0fff5;border-color:#c8f0d5;color:#126b37;">
            ✅ This website now includes your real QR image and real UPI ID.
          </div>
          <ul class="about-list" style="margin-top:18px;">
            <li>1. Add your food items to cart</li>
            <li>2. Click <strong>Proceed to Payment</strong></li>
            <li>3. Scan QR and pay total amount</li>
            <li>4. Click <strong>Send on WhatsApp</strong></li>
            <li>5. Your full order details go directly to your WhatsApp number</li>
          </ul>
          <div style="margin-top:18px; display:flex; gap:12px; flex-wrap:wrap;">
            <a class="btn btn-primary" href="upi://pay?pa=barmeshwarmaniya3@oksbi&pn=Barmeshwar%20Maniya&cu=INR" target="_blank">Open UPI App</a>
            <a class="btn btn-secondary" href="https://wa.me/919093252982?text=Hello%20Mammy%20Kitchen" target="_blank">Contact on WhatsApp</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section>
    <div class="container">
      <h2 class="section-title">Customer Reviews</h2>
      <p class="section-sub">Demo review section for your startup presentation</p>
      <div class="review-grid">
        <div class="review-card">
          <div class="stars">★★★★★</div>
          <p>“Very affordable and tasty lunch. Perfect for students during college time.”</p>
          <strong>- Student Customer</strong>
        </div>
        <div class="review-card">
          <div class="stars">★★★★★</div>
          <p>“Simple ordering and easy payment. WhatsApp order system is very helpful.”</p>
          <strong>- Polytechnic Student</strong>
        </div>
        <div class="review-card">
          <div class="stars">★★★★★</div>
          <p>“Good startup idea for institute food delivery. Budget-friendly and smart.”</p>
          <strong>- Campus User</strong>
        </div>
      </div>
    </div>
  </section>

  <section id="contact">
    <div class="container">
      <h2 class="section-title">Contact Mammy Kitchen</h2>
      <p class="section-sub">Connect directly for food orders and business inquiry</p>
      <div class="contact-box">
        <div class="contact-item">
          <h4>📞 WhatsApp / Mobile</h4>
          <p>9093252982</p>
        </div>
        <div class="contact-item">
          <h4>💳 UPI ID</h4>
          <p>barmeshwarmaniya3@oksbi</p>
        </div>
        <div class="contact-item">
          <h4>👨‍💼 Founder</h4>
          <p>Barmeshwar Maniya</p>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">
      <h3>Mammy Kitchen</h3>
      <p class="footer-note">Student Startup Food Website by Barmeshwar Maniya</p>
      <p class="footer-note">Real WhatsApp + Real UPI + Real QR Code Integrated</p>
    </div>
  </footer>

  <div class="float-wrap">
    <a class="float-btn wa" href="https://wa.me/919093252982?text=Hello%20Mammy%20Kitchen%2C%20I%20want%20to%20order%20food." target="_blank" title="WhatsApp">💬</a>
    <a class="float-btn pay" href="#payment" title="Payment">₹</a>
  </div>

  <div class="modal" id="paymentModal">
    <div class="modal-box">
      <h2 style="color:#9d0208; margin-bottom:10px;">Payment Instructions</h2>
      <p>Please pay the total amount using the QR code / UPI ID below:</p>
      <div class="qr-wrap" style="margin-top:16px;">
        <img src="my upi.jpeg" alt="UPI QR">
        <div class="upi-card">
          <p><strong>UPI ID:</strong> <span class="upi-id">barmeshwarmaniya3@oksbi</span></p>
          <p style="margin-top:8px;">Pay Total: <strong>₹<span id="modalTotal">0</span></strong></p>
        </div>
      </div>
      <div class="success">
        After payment, click “Send on WhatsApp” to share your order details and payment confirmation.
      </div>
      <div style="display:flex; gap:10px; flex-wrap:wrap; margin-top:18px;">
        <a class="btn btn-primary" id="upiDynamicLink" href="upi://pay?pa=barmeshwarmaniya3@oksbi&pn=Barmeshwar%20Maniya&cu=INR" target="_blank">Open UPI App</a>
        <button class="btn btn-secondary" onclick="closePaymentModal()">Close</button>
      </div>
    </div>
  </div>

  <script>
    const cart = {};

    function updateCartUI() {
      const cartList = document.getElementById('cartList');
      const totalAmountEl = document.getElementById('totalAmount');
      let total = 0;
      const items = Object.keys(cart).filter(name => cart[name].qty > 0);

      if (items.length === 0) {
        cartList.innerHTML = '<p style="color:#666;">No items added yet.</p>';
        totalAmountEl.textContent = '0';
        return;
      }

      cartList.innerHTML = items.map(name => {
        const item = cart[name];
        const subtotal = item.qty * item.price;
        total += subtotal;
        return `
          <div class="cart-item">
            <span>${name} x ${item.qty}</span>
            <strong>₹${subtotal}</strong>
          </div>
        `;
      }).join('');

      totalAmountEl.textContent = total;
    }

    document.querySelectorAll('.add-btn').forEach(btn => {
      btn.addEventListener('click', function() {
        const card = this.closest('.menu-card');
        const name = card.dataset.name;
        const price = parseInt(card.dataset.price);
        const qty = parseInt(card.querySelector('.qty-input').value) || 0;

        if (qty <= 0) {
          alert('Please enter quantity more than 0');
          return;
        }

        cart[name] = { price, qty };
        updateCartUI();
        alert(name + ' added to cart successfully!');
      });
    });

    function getTotalAmount() {
      let total = 0;
      Object.keys(cart).forEach(name => {
        total += cart[name].price * cart[name].qty;
      });
      return total;
    }

    function openPaymentModal() {
      const total = getTotalAmount();
      if (total <= 0) {
        alert('Please add food items first.');
        return;
      }
      document.getElementById('modalTotal').textContent = total;
      document.getElementById('upiDynamicLink').href = `upi://pay?pa=barmeshwarmaniya3@oksbi&pn=Barmeshwar%20Maniya&am=${total}&cu=INR`;
      document.getElementById('paymentModal').classList.add('active');
    }

    function closePaymentModal() {
      document.getElementById('paymentModal').classList.remove('active');
    }

    function sendWhatsAppOrder() {
      const name = document.getElementById('customerName').value.trim();
      const phone = document.getElementById('customerPhone').value.trim();
      const email = document.getElementById('customerEmail').value.trim();
      const institute = document.getElementById('customerInstitute').value.trim();
      const address = document.getElementById('customerAddress').value.trim();
      const total = getTotalAmount();

      if (!name || !phone || !email || !institute || !address) {
        alert('Please fill all customer details first.');
        return;
      }
      if (total <= 0) {
        alert('Please add at least one food item.');
        return;
      }

      const itemLines = Object.keys(cart)
        .filter(name => cart[name].qty > 0)
        .map(name => `- ${name} x ${cart[name].qty} = ₹${cart[name].qty * cart[name].price}`)
        .join('%0A');

      const message = `Hello Mammy Kitchen,%0A%0AI want to place an order.%0A%0A👤 Name: ${encodeURIComponent(name)}%0A📞 Mobile: ${encodeURIComponent(phone)}%0A📧 Email: ${encodeURIComponent(email)}%0A🏫 Institute: ${encodeURIComponent(institute)}%0A📍 Delivery Location: ${encodeURIComponent(address)}%0A%0A🍱 Order Items:%0A${itemLines}%0A%0A💰 Total Amount: ₹${total}%0A💳 Payment UPI: barmeshwarmaniya3@oksbi%0A%0A✅ I have completed / will complete payment and request order confirmation.`;

      window.open(`https://wa.me/919093252982?text=${message}`, '_blank');
    }

    window.addEventListener('click', function(e) {
      const modal = document.getElementById('paymentModal');
      if (e.target === modal) closePaymentModal();
    });
  </script>
</body>
</html>
