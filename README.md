<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
  <meta charset="UTF-8">
  <title>Wallet Clone - Blue & White Professional</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- Google Fonts for modern look -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary-blue: #1669c1;
      --blue-light: #eaf2fb;
      --white: #fff;
      --ash: #f4f6fa;
      --ash-dark: #e0e6ed;
      --success: #28c76f;
      --gray: #8c98a4;
      --border: #dbe6f3;
    }
    body {
      font-family: 'Inter', Arial, sans-serif;
      background: var(--blue-light);
      color: var(--primary-blue);
      margin: 0;
      min-height: 100vh;
    }
    .header {
      display: flex;
      align-items: center;
      padding: 1.2rem 1.1rem 0.4rem 1.1rem;
      background: var(--white);
      border-bottom: 1px solid var(--border);
      box-shadow: 0 2px 10px rgba(22,105,193,0.05);
    }
    .bell, .menu, .profile {
      width: 34px;
      height: 34px;
      background: var(--ash);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-right: 12px;
      position: relative;
    }
    .bell-dot {
      position: absolute;
      top: 8px;
      right: 7px;
      width: 8px;
      height: 8px;
      background: var(--primary-blue);
      border-radius: 50%;
    }
    .profile {
      background: linear-gradient(135deg, #6db3f2 40%, #1e69c1 100%);
    }
    .email {
      font-size: 16px;
      color: var(--primary-blue);
      margin: 0 10px;
      flex: 1;
      font-weight: 600;
      white-space: nowrap;
    }
    .search-bar {
      margin: 18px 16px 0 16px;
      background: var(--ash);
      border-radius: 8px;
      padding: 13px 14px;
      color: var(--gray);
      border: none;
      width: calc(100% - 32px);
      font-size: 14px;
    }
    .section {
      margin: 21px 16px 90px 16px;
    }
    .wallet-title {
      color: var(--gray);
      font-size: 1.1rem;
      margin-bottom: 6px;
    }
    .wallet-balance {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
    }
    .wallet-balance .balance {
      font-weight: bold;
      font-size: 2.2rem;
      color: var(--primary-blue);
    }
    .wallet-balance .currency {
      font-size: 1.2rem;
      color: var(--gray);
      font-weight: 400;
      margin-left: 6px;
    }
    .wallet-balance .percent {
      color: var(--success);
      font-size: 1.1rem;
      margin-right: 12px;
      font-weight: 600;
    }
    .actions {
      display: flex;
      justify-content: space-between;
      margin: 30px 0 10px 0;
      gap: 12px;
    }
    .action-btn {
      background: var(--ash);
      color: var(--primary-blue);
      border: none;
      border-radius: 16px;
      width: 65px;
      height: 65px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-size: 15px;
      box-shadow: 0 1px 8px rgba(22,105,193,0.07);
      cursor: not-allowed;
      transition: background 0.1s, color 0.1s;
      opacity: 0.65;
      position: relative;
    }
    .action-btn.withdrawal {
      background: var(--success);
      color: #fff;
      font-weight: 600;
      cursor: pointer;
      opacity: 1;
      border: 2px solid #16a34a;
      box-shadow: 0 2px 12px rgba(40,199,111,0.13);
    }
    .action-label {
      margin-top: 5px;
      font-size: 15px;
      color: var(--primary-blue);
      font-weight: 500;
    }
    .action-btn.withdrawal .action-label {
      color: #fff;
    }
    .history {
      background: var(--ash-dark);
      border-radius: 11px;
      padding: 10px 18px;
      margin: 18px 0 0 0;
      font-size: 16px;
      color: var(--gray);
    }
    .cards {
      display: flex;
      gap: 14px;
      margin: 18px 0 0 0;
    }
    .card {
      background: var(--white);
      border-radius: 16px;
      padding: 20px 13px;
      flex: 1;
      text-align: center;
      font-size: 15px;
      color: var(--primary-blue);
      min-width: 0;
      border: 1px solid var(--border);
      box-shadow: 0 1px 5px rgba(22,105,193,0.04);
    }
    .card-title {
      font-size: 17px;
      font-weight: 600;
      color: var(--primary-blue);
      margin-bottom: 9px;
    }
    .amount {
      font-size: 18px;
      margin: 7px 0 2px 0;
      color: var(--primary-blue);
      font-weight: 500;
    }
    .card-desc {
      color: var(--gray);
      font-size: 14px;
    }
    .footer {
      position: fixed;
      width: 100%;
      bottom: 0;
      left: 0;
      background: var(--white);
      display: flex;
      justify-content: space-around;
      align-items: center;
      border-top: 1px solid var(--border);
      padding: 7px 0 4px 0;
      z-index: 10;
      box-shadow: 0 -2px 12px rgba(22,105,193,0.07);
    }
    .footer-btn {
      display: flex;
      flex-direction: column;
      align-items: center;
      color: var(--gray);
      font-size: 13px;
      text-decoration: none;
      font-weight: 500;
      transition: color 0.15s;
    }
    .footer-btn.active {
      color: var(--primary-blue);
    }
    .footer-center {
      background: var(--primary-blue);
      width: 56px;
      height: 56px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-top: -30px;
      border: 2px solid var(--blue-light);
      font-size: 30px;
      color: #fff;
      box-shadow: 0 2px 12px rgba(22,105,193,0.13);
    }
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0; width: 100vw; height: 100vh;
      background: rgba(22,105,193,0.18);
      align-items: center; justify-content: center;
      z-index: 999;
    }
    .modal-content {
      background: #fff;
      padding: 36px 28px;
      border-radius: 14px;
      text-align: center;
      font-size: 21px;
      color: var(--primary-blue);
      font-weight: 700;
      box-shadow: 0 2px 18px rgba(22,105,193,0.13);
    }
    @media (max-width: 600px) {
      .section {margin-bottom: 110px;}
      .cards {flex-direction: column;}
    }
  </style>
</head>
<body>
  <div class="header">
    <div class="bell">
      <svg width="20" height="20" fill="#1669c1"><circle cx="10" cy="13" r="7" /></svg>
      <span class="bell-dot"></span>
    </div>
    <div class="menu">
      <svg width="20" height="20" fill="#1669c1"><rect width="18" height="3" y="4"/><rect width="18" height="3" y="10"/><rect width="18" height="3" y="16"/></svg>
    </div>
    <span class="email">f***@gm...</span>
    <div class="profile"></div>
  </div>
  <input class="search-bar" type="text" placeholder="Search account activity and more...">
  <div class="section">
    <div class="wallet-title">Account Wallet</div>
    <div class="wallet-balance">
      <div class="percent">(+ $32) 6864% &uarr;</div>
      <div>
        <span class="balance">$2,000</span>
        <span class="currency">USDT</span>
      </div>
    </div>
    <div class="actions">
      <button class="action-btn" disabled>
        <div>
          <svg width="27" height="27" fill="#b8b8b8"><rect width="19" height="4" x="4" y="12"/></svg>
        </div>
        <div class="action-label">Buy/Sell</div>
      </button>
      <button class="action-btn" disabled>
        <div>
          <svg width="27" height="27" fill="#b8b8b8"><rect width="19" height="4" x="4" y="12" transform="rotate(90 13.5 13.5)"/></svg>
        </div>
        <div class="action-label">Swap</div>
      </button>
      <button class="action-btn" disabled>
        <div>
          <svg width="27" height="27" fill="#b8b8b8"><polygon points="13.5,22 24,7 3,7"/></svg>
        </div>
        <div class="action-label">Receive</div>
      </button>
      <button class="action-btn withdrawal" id="withdrawBtn">
        <div>
          <svg width="27" height="27" fill="#fff"><polygon points="13.5,4 24,20 3,20"/></svg>
        </div>
        <div class="action-label">Withdraw</div>
      </button>
    </div>
    <div class="history">
      <span>one month ago</span>
    </div>
    <div class="cards">
      <div class="card">
        <div class="card-title">Loans</div>
        <div class="amount">$10,000</div>
        <div class="card-desc">Available for lending</div>
      </div>
      <div class="card">
        <div class="card-title">Savings</div>
        <div class="amount">up to 10%</div>
        <div class="card-desc">Start earning now...</div>
      </div>
    </div>
  </div>
  <div class="footer">
    <a href="#" class="footer-btn active">
      <svg width="24" height="24" fill="currentColor"><circle cx="12" cy="12" r="10"/></svg>
      Home
    </a>
    <a href="#" class="footer-btn">
      <svg width="24" height="24" fill="currentColor"><rect x="3" y="3" width="18" height="18" rx="5"/></svg>
      Assets
    </a>
    <div class="footer-center">
      <span style="font-size: 30px;">⇅</span>
    </div>
    <a href="#" class="footer-btn">
      <svg width="24" height="24" fill="currentColor"><circle cx="12" cy="7" r="5"/><rect x="7" y="13" width="10" height="7" rx="3"/></svg>
      Contacts
    </a>
    <a href="#" class="footer-btn">
      <svg width="24" height="24" fill="currentColor"><rect width="18" height="18" x="3" y="3" rx="5"/></svg>
      Discover
    </a>
  </div>
  <div class="modal" id="modal">
    <div class="modal-content">
      $60 USDT needed to unlock payment
    </div>
  </div>
  <script>
    const withdrawBtn = document.getElementById('withdrawBtn');
    const modal = document.getElementById('modal');
    withdrawBtn.addEventListener('click', function() {
      modal.style.display = 'flex';
      setTimeout(() => { modal.style.display = 'none'; }, 3000);
    });
  </script>
</body>
</html>
