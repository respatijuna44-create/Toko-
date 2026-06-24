<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KEDAI ANGGINAMI</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #f8f0e3;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Quicksand', sans-serif;
            padding: 20px;
        }

        /* ===== LOGIN CARD ===== */
        .login-card {
            max-width: 400px;
            width: 100%;
            background: #fffcf7;
            border-radius: 48px;
            padding: 40px 32px 36px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.12), 0 8px 16px rgba(0, 0, 0, 0.06);
            border: 2px solid #f0d5b0;
            text-align: center;
            display: block;
        }

        .login-card .logo {
            font-size: 2.8rem;
            margin-bottom: 4px;
        }

        .login-card h1 {
            font-size: 1.8rem;
            font-weight: 700;
            color: #3d2b1c;
            letter-spacing: 1px;
            margin-bottom: 4px;
        }

        .login-card .sub {
            font-size: 0.95rem;
            color: #7a5f47;
            margin-bottom: 24px;
            font-weight: 500;
        }

        .login-card .sub span {
            background: #e6d4bd;
            padding: 0 12px;
            border-radius: 40px;
            font-weight: 600;
            color: #4d321e;
        }

        .login-form {
            display: flex;
            flex-direction: column;
            gap: 14px;
        }

        .login-form .input-group {
            display: flex;
            align-items: center;
            background: white;
            border-radius: 60px;
            padding: 4px 18px 4px 16px;
            border: 2px solid #e0cdb8;
            transition: 0.15s;
        }

        .login-form .input-group:focus-within {
            border-color: #b45f2b;
            box-shadow: 0 0 0 4px rgba(180, 95, 43, 0.12);
        }

        .login-form .input-group .icon {
            font-size: 1.1rem;
            margin-right: 10px;
            color: #7a5f47;
        }

        .login-form .input-group input {
            border: none;
            background: transparent;
            padding: 14px 0;
            font-size: 0.95rem;
            font-family: 'Quicksand', sans-serif;
            font-weight: 500;
            color: #2d1f12;
            width: 100%;
            outline: none;
        }

        .login-form .input-group input::placeholder {
            color: #b8a18b;
            font-weight: 400;
        }

        .login-form .btn-login {
            border: none;
            padding: 14px 0;
            border-radius: 60px;
            font-family: 'Quicksand', sans-serif;
            font-weight: 700;
            font-size: 1rem;
            cursor: pointer;
            transition: 0.15s;
            letter-spacing: 1px;
            background: #b45f2b;
            color: white;
            box-shadow: 0 4px 12px rgba(180, 95, 43, 0.25);
            margin-top: 6px;
        }

        .login-form .btn-login:hover {
            background: #9e4f22;
            transform: translateY(-2px);
            box-shadow: 0 6px 16px rgba(180, 95, 43, 0.3);
        }

        .login-form .btn-login:active {
            transform: translateY(0);
        }

        .login-status {
            margin-top: 14px;
            font-size: 0.85rem;
            font-weight: 600;
            color: #1f6e4a;
            min-height: 28px;
        }

        .login-status.error {
            color: #b13e3e;
        }

        .login-status .hint {
            font-weight: 400;
            color: #8f7a66;
            font-size: 0.75rem;
            background: #f5ede3;
            padding: 4px 16px;
            border-radius: 40px;
            display: inline-block;
        }

        .login-card .footer-note {
            margin-top: 24px;
            font-size: 0.7rem;
            color: #ad927b;
            border-top: 1px dashed #e6d4bd;
            padding-top: 16px;
            letter-spacing: 0.5px;
        }

        /* ===== MENU CARD ===== */
        .menu-card {
            max-width: 480px;
            width: 100%;
            background: #fffcf7;
            border-radius: 48px 48px 32px 32px;
            padding: 28px 24px 32px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.12), 0 8px 16px rgba(0, 0, 0, 0.06);
            border: 2px solid #f0d5b0;
            display: none;
        }

        .menu-header {
            text-align: center;
            margin-bottom: 18px;
            position: relative;
        }

        .menu-header h1 {
            font-size: 2rem;
            font-weight: 700;
            letter-spacing: 1.5px;
            color: #3d2b1c;
            text-transform: uppercase;
            background: linear-gradient(135deg, #b45f2b, #7a3e1a);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: inline-block;
            padding: 0 12px;
            position: relative;
        }

        .menu-header .sub-judul {
            font-size: 1.7rem;
            font-weight: 600;
            color: #3d2b1c;
            letter-spacing: 2px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            margin-top: -6px;
        }

        .menu-header .sub-judul span {
            background: #e6d4bd;
            padding: 0 16px;
            border-radius: 60px;
            font-size: 1.2rem;
            color: #4d321e;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 14px 12px;
            margin-top: 10px;
        }

        .menu-item {
            background: #fdf8f2;
            border-radius: 24px;
            padding: 16px 8px 12px;
            text-align: center;
            box-shadow: inset 0 -2px 0 #e2ceb8, 0 4px 8px rgba(0, 0, 0, 0.02);
            border: 1px solid #f0e0ce;
            transition: 0.1s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 110px;
        }

        .menu-item:hover {
            background: #fcf4ea;
            border-color: #dbbd9e;
        }

        .menu-item .harga {
            font-weight: 700;
            font-size: 1.1rem;
            background: #b45f2b;
            color: white;
            padding: 2px 14px;
            border-radius: 40px;
            display: inline-block;
            margin-bottom: 6px;
            letter-spacing: 0.5px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
            line-height: 1.6;
        }

        .menu-item .nama {
            font-weight: 600;
            font-size: 0.9rem;
            color: #2d1f12;
            line-height: 1.3;
            padding: 0 4px;
            word-break: break-word;
        }

        .menu-item.full-width {
            grid-column: 1 / -1;
            flex-direction: row;
            flex-wrap: wrap;
            justify-content: center;
            gap: 4px 14px;
            padding: 12px 8px;
            min-height: 70px;
        }

        .menu-item.full-width .harga {
            margin-bottom: 0;
        }

        .menu-item.gabung .nama {
            font-size: 0.8rem;
            line-height: 1.4;
        }

        .menu-divider {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            margin: 14px 0 10px;
        }

        .menu-divider span {
            display: inline-block;
            height: 3px;
            width: 30px;
            background: #dbbd9e;
            border-radius: 10px;
        }

        .menu-divider .icon-minum {
            font-size: 1.3rem;
            filter: drop-shadow(0 2px 2px rgba(0, 0, 0, 0.1));
        }

        .lokasi-section {
            margin-top: 18px;
            background: #e7ddd0;
            border-radius: 60px;
            padding: 12px 18px;
            border: 1px solid #d6bea6;
            box-shadow: inset 0 2px 6px rgba(255, 245, 235, 0.6);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            flex-wrap: wrap;
        }

        .lokasi-section .label-lokasi {
            font-weight: 600;
            color: #3d281b;
            background: #fcf4ea;
            padding: 4px 18px 4px 14px;
            border-radius: 40px;
            font-size: 0.85rem;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            border: 1px solid #d6bea6;
        }

        .lokasi-section .nama-lokasi {
            font-weight: 700;
            font-size: 1rem;
            color: #3d2b1c;
            letter-spacing: 0.3px;
            background: #fffcf7;
            padding: 4px 20px 4px 16px;
            border-radius: 40px;
            border: 1px solid #d6bea6;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.03);
        }

        .lokasi-section .nama-lokasi small {
            font-weight: 400;
            font-size: 0.7rem;
            color: #7a5f47;
            margin-left: 4px;
        }

        .owner-section {
            margin-top: 18px;
            background: #f5ede3;
            border-radius: 60px;
            padding: 14px 18px;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            gap: 12px 18px;
            border: 1px solid #e5d2bb;
            box-shadow: inset 0 2px 4px rgba(255, 255, 255, 0.7);
        }

        .owner-item {
            display: flex;
            align-items: center;
            gap: 6px;
            font-size: 0.8rem;
            font-weight: 600;
            color: #3d281b;
            background: white;
            padding: 4px 16px 4px 12px;
            border-radius: 40px;
            box-shadow: 0 1px 4px rgba(0, 0, 0, 0.03);
            border: 1px solid #e6d2bd;
        }

        .owner-item .label {
            font-weight: 400;
            color: #7a5f47;
            margin-right: 2px;
        }

        .owner-item .value {
            font-weight: 700;
            color: #3d2b1c;
            letter-spacing: 0.3px;
        }

        .owner-item.email .value {
            font-size: 0.7rem;
        }

        .garis-bawah {
            width: 60px;
            height: 3px;
            background: #dbbd9e;
            margin: 8px auto 2px;
            border-radius: 10px;
        }

        .menu-item.drink {
            background: #e7f0eb;
            border-color: #b9cfc0;
        }
        .menu-item.drink .harga {
            background: #1f6e4a;
        }

        .menu-item .harga+.nama {
            margin-top: 4px;
        }

        .footer-note {
            margin-top: 20px;
            text-align: center;
            font-size: 0.7rem;
            color: #ad927b;
            letter-spacing: 1px;
            border-top: 1px dashed #e6d4bd;
            padding-top: 16px;
        }

        .logout-wrapper {
            text-align: right;
            margin-bottom: 10px;
        }

        .btn-logout {
            border: none;
            background: #e0cdb8;
            color: #3d281b;
            padding: 6px 20px;
            border-radius: 60px;
            font-family: 'Quicksand', sans-serif;
            font-weight: 700;
            font-size: 0.75rem;
            cursor: pointer;
            transition: 0.15s;
            border: 1px solid #d6bea6;
        }

        .btn-logout:hover {
            background: #d0bb9e;
        }

        @media (max-width: 420px) {
            .login-card {
                padding: 32px 20px 28px;
            }
            .login-card h1 {
                font-size: 1.5rem;
            }
            .login-form .input-group input {
                font-size: 0.85rem;
                padding: 12px 0;
            }
            .menu-card {
                padding: 20px 14px;
            }
            .menu-item .nama {
                font-size: 0.75rem;
            }
            .menu-item .harga {
                font-size: 0.9rem;
                padding: 0 12px;
            }
            .owner-item {
                font-size: 0.7rem;
                padding: 4px 12px;
            }
            .menu-header h1 {
                font-size: 1.6rem;
            }
            .menu-header .sub-judul {
                font-size: 1.3rem;
            }
            .lokasi-section .nama-lokasi {
                font-size: 0.85rem;
                padding: 4px 14px;
            }
            .lokasi-section .label-lokasi {
                font-size: 0.75rem;
                padding: 4px 12px;
            }
        }
    </style>
</head>
<body>
    <!-- ===== LOGIN CARD ===== -->
    <div class="login-card" id="loginCard">
        <div class="logo">🥤</div>
        <h1>KEDAI ANGGINAMI</h1>
        <div class="sub">Masuk ke <span>menu toko</span></div>

        <form class="login-form" id="loginForm">
            <div class="input-group">
                <span class="icon">✉️</span>
                <input type="email" id="loginEmail" placeholder="Email" value="arjunarespati@gmail.com" required autofocus>
            </div>
            <div class="input-group">
                <span class="icon">🔑</span>
                <input type="password" id="loginPassword" placeholder="Password" value="junajuna29" required>
            </div>
            <button type="button" class="btn-login" onclick="handleLogin()">MASUK</button>
            <div class="login-status" id="loginStatus">
                <span class="hint">🔑 password: junajuna29</span>
            </div>
        </form>

        <div class="footer-note">
            ⚡ selamat datang ⚡
        </div>
    </div>

    <!-- ===== MENU CARD ===== -->
    <div class="menu-card" id="menuCard">
        <div class="logout-wrapper">
            <button class="btn-logout" onclick="handleLogout()">🚪 KELUAR</button>
        </div>

        <div class="menu-header">
            <h1>MENU TERSEDIA</h1>
            <div class="sub-judul">
                <span>KEDAI ANGGINAMI</span>
                <span class="emoji-besar">🥤</span>
            </div>
            <div class="garis-bawah"></div>
        </div>

        <div class="menu-grid">
            <div class="menu-item">
                <span class="harga">5K</span>
                <span class="nama">BURGER MINI</span>
            </div>
            <div class="menu-item">
                <span class="harga">5K</span>
                <span class="nama">PISANG CRISPY</span>
            </div>
            <div class="menu-item full-width">
                <span class="harga">5K</span>
                <span class="nama" style="font-size:0.9rem;">CIRENG ISI AYAM SUWIR &amp; KEJU MOZARELLA</span>
            </div>
            <div class="menu-item gabung" style="grid-column: 1 / -1; background: #fcf3e9;">
                <span class="harga">1K</span>
                <span class="nama" style="font-size:0.9rem;">TELUR GULUNG &amp; BIHUN GULUNG</span>
            </div>
            <div class="menu-item">
                <span class="harga">5K</span>
                <span class="nama">BAKARAN SATE</span>
            </div>
            <div class="menu-item">
                <span class="harga">5K</span>
                <span class="nama">MAKLOR <span style="display:block; font-weight:400; font-size:0.7rem;">(MAKARONI TELOR)</span></span>
            </div>
            <div class="menu-item">
                <span class="harga">5K</span>
                <span class="nama">BASO ACI</span>
            </div>
            <div class="menu-item">
                <span class="harga">5K</span>
                <span class="nama">BANANA ROLL</span>
            </div>
            <div class="menu-item">
                <span class="harga">3K</span>
                <span class="nama">SOSIS SEDANG</span>
            </div>
            <div class="menu-item drink">
                <span class="harga">3K</span>
                <span class="nama">ES TEH JUMBO</span>
            </div>
        </div>

        <div class="menu-divider">
            <span></span>
            <span class="icon-minum">🧋</span>
            <span></span>
        </div>

        <div class="lokasi-section">
            <span class="label-lokasi">📍 LOKASI</span>
            <span class="nama-lokasi">
                Warung Makan Mamih Sederhana
                <small>(Executive)</small>
            </span>
        </div>

        <div class="owner-section">
            <div class="owner-item">
                <span class="label">👤</span>
                <span class="value">Arjuna Dwi Respati</span>
            </div>
            <div class="owner-item email">
                <span class="label">✉️</span>
                <span class="value">arjunarespati@gmail.com</span>
            </div>
            <div class="owner-item">
                <span class="label">📞</span>
                <span class="value">085837622364</span>
            </div>
        </div>

        <div class="footer-note">
            ⚡ selamat menikmati ⚡
        </div>
    </div>

    <script>
        // ===== KREDENSIAL =====
        const VALID_EMAIL = 'arjunarespati@gmail.com';
        const VALID_PASSWORD = 'junajuna29';

        const loginCard = document.getElementById('loginCard');
        const menuCard = document.getElementById('menuCard');
        const loginEmail = document.getElementById('loginEmail');
        const loginPassword = document.getElementById('loginPassword');
        const loginStatus = document.getElementById('loginStatus');

        // ===== FUNGSI LOGIN =====
        function handleLogin() {
            const email = loginEmail.value.trim();
            const pass = loginPassword.value.trim();

            if (email === VALID_EMAIL && pass === VALID_PASSWORD) {
                sessionStorage.setItem('kedaiLogin', 'true');
                showMenu();
                loginStatus.innerHTML = '<span class="hint">✅ Login berhasil! Selamat datang.</span>';
                loginStatus.className = 'login-status';
            } else {
                loginStatus.innerHTML = '❌ Email atau password salah. Coba lagi.';
                loginStatus.className = 'login-status error';
                loginPassword.value = '';
                loginPassword.focus();
                setTimeout(() => {
                    if (!loginStatus.classList.contains('error')) return;
                    loginStatus.innerHTML = '<span class="hint">🔑 password: junajuna29</span>';
                    loginStatus.className = 'login-status';
                }, 3000);
            }
        }

        // ===== FUNGSI LOGOUT =====
        function handleLogout() {
            sessionStorage.removeItem('kedaiLogin');
            showLogin();
        }

        // ===== TAMPILKAN MENU =====
        function showMenu() {
            loginCard.style.display = 'none';
            menuCard.style.display = 'block';
        }

        // ===== TAMPILKAN LOGIN =====
        function showLogin() {
            loginCard.style.display = 'block';
            menuCard.style.display = 'none';
            loginEmail.value = 'arjunarespati@gmail.com';
            loginPassword.value = 'junajuna29';
            loginStatus.innerHTML = '<span class="hint">🔑 password: junajuna29</span>';
            loginStatus.className = 'login-status';
        }

        // ===== CEK SESSION SAAT LOAD =====
        if (sessionStorage.getItem('kedaiLogin') === 'true') {
            showMenu();
        } else {
            showLogin();
        }

        // ===== TAMBAHKAN EVENT LISTENER UNTUK ENTER =====
        document.getElementById('loginForm').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                e.preventDefault();
                handleLogin();
            }
        });
    </script>
</body>
</html>
