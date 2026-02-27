<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
  <title>KIFA+ Mobile</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Roboto, system-ui, -apple-system, Helvetica, sans-serif;
    }

    body {
      background: linear-gradient(145deg, #f0f4fa 0%, #d9e2ef 100%);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 16px;
    }

    .mobile-container {
      max-width: 400px;
      width: 100%;
      background: rgba(255,255,255,0.7);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      border-radius: 42px;
      box-shadow: 0 25px 50px -8px rgba(0,20,50,0.25), 
                  inset 0 0 0 1px rgba(255,255,255,0.6);
      overflow: hidden;
      padding: 24px 20px 30px;
      border: 1px solid rgba(255,255,255,0.5);
    }

    .status-bar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 15px;
      font-weight: 500;
      color: #1e2b3c;
      padding: 0 6px 12px;
      letter-spacing: 0.2px;
    }

    .time {
      font-weight: 600;
      background: rgba(0,0,0,0.03);
      padding: 4px 12px;
      border-radius: 30px;
    }

    .icons {
      display: flex;
      gap: 6px;
    }

    .icon-circle {
      width: 18px;
      height: 18px;
      background: #1e2b3c;
      opacity: 0.3;
      border-radius: 50%;
    }

    .logo-area {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin: 10px 0 20px;
    }

    .logo-icon {
      width: 80px;
      height: 80px;
      background: linear-gradient(145deg, #2a4b7c, #1c3b5e);
      border-radius: 28px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 44px;
      font-weight: 700;
      box-shadow: 0 15px 20px -5px rgba(0,32,64,0.3);
      margin-bottom: 12px;
    }

    .logo-text {
      font-size: 28px;
      font-weight: 700;
      color: #0b2a44;
      letter-spacing: 1px;
    }

    .badge {
      background: #2b4d71;
      color: white;
      padding: 4px 16px;
      border-radius: 40px;
      font-size: 14px;
      font-weight: 600;
      margin-top: 6px;
    }

    .balance-card {
      background: linear-gradient(115deg, #1c3c5e, #2b5580);
      border-radius: 32px;
      padding: 22px 20px;
      color: white;
      margin: 20px 0 16px;
      box-shadow: 0 15px 20px -5px rgba(20,60,100,0.5);
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .balance-label {
      font-size: 16px;
      opacity: 0.8;
      letter-spacing: 0.5px;
    }

    .balance-number {
      font-size: 42px;
      font-weight: 800;
      line-height: 1;
    }

    .balance-footer {
      display: flex;
      justify-content: space-between;
      margin-top: 8px;
      font-size: 15px;
    }

    .section-title {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin: 28px 0 12px;
    }

    .section-title h3 {
      font-size: 20px;
      font-weight: 700;
      color: #1e2f40;
    }

    .section-title a {
      color: #2b4d71;
      font-size: 15px;
      font-weight: 500;
      text-decoration: none;
      opacity: 0.8;
    }

    .card-grid {
      display: flex;
      flex-direction: column;
      gap: 14px;
    }

    .card {
      background: rgba(255,255,255,0.6);
      backdrop-filter: blur(8px);
      -webkit-backdrop-filter: blur(8px);
      border-radius: 28px;
      padding: 18px 18px;
      border: 1px solid rgba(255,255,255,0.7);
      box-shadow: 0 6px 12px rgba(0,20,40,0.08);
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .card-content {
      display: flex;
      align-items: center;
      gap: 16px;
    }

    .card-emoji {
      width: 52px;
      height: 52px;
      background: #eef3fc;
      border-radius: 24px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 28px;
    }

    .card-info h4 {
      font-size: 18px;
      font-weight: 700;
      color: #0d2a41;
    }

    .card-info p {
      font-size: 14px;
      color: #4a5e74;
      margin-top: 4px;
    }

    .card-arrow {
      font-size: 24px;
      color: #2b4d71;
      opacity: 0.7;
    }

    .floating-btn {
      background: #1d3b5a;
      color: white;
      width: 60px;
      height: 60px;
      border-radius: 40px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 32px;
      box-shadow: 0 10px 18px #0b2a4480;
      margin: 10px auto -10px;
      border: 2px solid white;
    }

    .bottom-nav {
      display: flex;
      justify-content: space-around;
      background: rgba(255,255,255,0.65);
      backdrop-filter: blur(15px);
      -webkit-backdrop-filter: blur(15px);
      border-radius: 40px;
      padding: 10px 8px;
      margin-top: 30px;
      border: 1px solid rgba(255,255,255,0.8);
    }

    .nav-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 4px;
      color: #2f4a6b;
      font-size: 12px;
      font-weight: 500;
      opacity: 0.7;
      transition: 0.2s;
    }

    .nav-item.active {
      opacity: 1;
      color: #1d3b5a;
      font-weight: 600;
    }

    .nav-icon {
      font-size: 24px;
    }
  </style>
</head>
<body>
  <div class="mobile-container">
    <div class="status-bar">
      <span class="time">9:41</span>
      <div class="icons">
        <span class="icon-circle"></span>
        <span class="icon-circle"></span>
        <span class="icon-circle"></span>
      </div>
    </div>

    <div class="logo-area">
      <div class="logo-icon">K+</div>
      <div class="logo-text">KIFA+</div>
      <span class="badge">PREMIUM • 5G</span>
    </div>

    <div class="balance-card">
      <span class="balance-label">Current Balance</span>
      <div class="balance-number">SAR 185.75</div>
      <div class="balance-footer">
        <span>📶 Unlimited 5G</span>
        <span>⏳ Renews in 12 days</span>
      </div>
    </div>

    <div class="section-title">
      <h3>Quick Services</h3>
      <a href="#">See all</a>
    </div>

    <div class="card-grid">
      <div class="card">
        <div class="card-content">
          <div class="card-emoji">📱</div>
          <div class="card-info">
            <h4>Top Up</h4>
            <p>For yourself or others</p>
          </div>
        </div>
        <div class="card-arrow">→</div>
      </div>
      <div class="card">
        <div class="card-content">
          <div class="card-emoji">🌐</div>
          <div class="card-info">
            <h4>Data Plans</h4>
            <p>Social, calls, bundles</p>
          </div>
        </div>
        <div class="card-arrow">→</div>
      </div>
      <div class="card">
        <div class="card-content">
          <div class="card-emoji">📞</div>
          <div class="card-info">
            <h4>Support</h4>
            <p>24/7 live assistance</p>
          </div>
        </div>
        <div class="card-arrow">→</div>
      </div>
    </div>

    <div class="section-title" style="margin-top:20px">
      <h3>KIFA+ Offers</h3>
      <a href="#">More</a>
    </div>

    <div style="background:rgba(255,255,240,0.5); border-radius:26px; padding:16px;">
      <div style="display:flex; gap:12px; align-items:center;">
        <span style="font-size:40px;">🎁</span>
        <div>
          <h4 style="color:#1f3a5f;">Welcome Gift</h4>
          <p style="color:#2d4b6e;">Get 20 GB free on first subscription</p>
        </div>
      </div>
    </div>

    <div style="display:flex; justify-content:center; margin-top:20px;">
      <div class="floating-btn">+</div>
    </div>

    <div class="bottom-nav">
      <div class="nav-item active">
        <span class="nav-icon">🏠</span>
        <span>Home</span>
      </div>
      <div class="nav-item">
        <span class="nav-icon">📊</span>
        <span>Usage</span>
      </div>
      <div class="nav-item">
        <span class="nav-icon">🛒</span>
        <span>Shop</span>
      </div>
      <div class="nav-item">
        <span class="nav-icon">👤</span>
        <span>Profile</span>
      </div>
    </div>

    <div style="text-align:center; margin-top:12px; color:#6783a0; font-size:12px;">
      KIFA+ Mobile • v2.3
    </div>
  </div>
</body>
</html>
