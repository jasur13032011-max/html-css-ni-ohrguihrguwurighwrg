# html-css-ni-ohrguihrguwurighwrg
Mana, Boshqaruv paneli (Dashboard) uchun so'ralgan talablar asosida tayyorlangan to'liq responsive HTML va CSS kodlari.

1. HTML fayli (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard — Boshqaruv Paneli</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="dashboard">

    <aside class="sidebar">
        <div class="sidebar__logo">
            <h2>AdminPanel</h2>
        </div>
        <nav class="sidebar__nav">
            <a href="#" class="sidebar__link sidebar__link--active">Bosh sahifa</a>
            <a href="#" class="sidebar__link">Tahlillar</a>
            <a href="#" class="sidebar__link">Buyurtmalar</a>
            <a href="#" class="sidebar__link">Foydalanuvchilar</a>
            <a href="#" class="sidebar__link">Sozlamalar</a>
        </nav>
        <div class="sidebar__profile">
            <div class="sidebar__avatar">A</div>
            <div class="sidebar__user-info">
                <span class="sidebar__user-name">Asrorbek</span>
                <span class="sidebar__user-role">Administrator</span>
            </div>
        </div>
    </aside>

    <main class="main-content">
        
        <header class="header">
            <h1 class="header__title">Bosh sahifa</h1>
            <div class="header__actions">
                <div class="header__search-box">
                    <input type="text" class="header__search" placeholder="Qidirish...">
                </div>
                <button class="header__notifications" aria-label="Bildirishnomalar">
                    🔔 <span class="header__badge">3</span>
                </button>
            </div>
        </header>

        <section class="stats-grid">
            <div class="stat-card">
                <span class="stat-card__icon">👥</span>
                <div class="stat-card__details">
                    <span class="stat-card__title">Foydalanuvchilar</span>
                    <span class="stat-card__value">12,450</span>
                </div>
            </div>
            <div class="stat-card">
                <span class="stat-card__icon">💰</span>
                <div class="stat-card__details">
                    <span class="stat-card__title">Daromad</span>
                    <span class="stat-card__value">$45,230</span>
                </div>
            </div>
            <div class="stat-card">
                <span class="stat-card__icon">📦</span>
                <div class="stat-card__details">
                    <span class="stat-card__title">Buyurtmalar</span>
                    <span class="stat-card__value">1,120</span>
                </div>
            </div>
            <div class="stat-card">
                <span class="stat-card__icon">📈</span>
                <div class="stat-card__details">
                    <span class="stat-card__title">O'sish</span>
                    <span class="stat-card__value">+24.5%</span>
                </div>
            </div>
        </section>

        <section class="table-container">
            <h3 class="table-container__title">Oxirgi tranzaksiyalar</h3>
            <div class="table-responsive">
                <table class="data-table">
                    <thead>
                        <tr>
                            <th>Mijoz</th>
                            <th>Sana</th>
                            <th>Suma</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Alisher Navoiy</td>
                            <td>06.07.2026</td>
                            <td>$1,200</td>
                            <td><span class="status-badge status-badge--success">Bajarildi</span></td>
                        </tr>
                        <tr>
                            <td>Zuhra Umarova</td>
                            <td>05.07.2026</td>
                            <td>$450</td>
                            <td><span class="status-badge status-badge--pending">Kutilmoqda</span></td>
                        </tr>
                        <tr>
                            <td>Jasur Aliyev</td>
                            <td>04.07.2026</td>
                            <td>$890</td>
                            <td><span class="status-badge status-badge--success">Bajarildi</span></td>
                        </tr>
                        <tr>
                            <td>Madina Sobirova</td>
                            <td>02.07.2026</td>
                            <td>$150</td>
                            <td><span class="status-badge status-badge--danger">Rad etildi</span></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

    </main>

</body>
</html>
2. CSS fayli (style.css)
CSS
/* Custom Properties (Variables) */
:root {
    --bg-main: #f8fafc;
    --bg-sidebar: #0f172a;
    --text-light: #f1f5f9;
    --text-muted: #64748b;
    --text-dark: #1e293b;
    --primary: #3b82f6;
    --white: #ffffff;
    --border-color: #e2e8f0;
    
    --success: #10b981;
    --success-bg: #d1fae5;
    --pending: #f59e0b;
    --pending-bg: #fef3c7;
    --danger: #ef4444;
    --danger-bg: #fee2e2;
}

/* Reset elementlari */
*, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: var(--bg-main);
    color: var(--text-dark);
}

/* ========================================================
   5. CSS GRID BILAN 2 USTUNLI LAYOUT
   ======================================================== */
.dashboard {
    display: grid;
    grid-template-columns: 260px 1fr;
    min-height: 100vh;
}

/* ========================================================
   1. STICKY SIDEBAR
   ======================================================== */
.sidebar {
    background-color: var(--bg-sidebar);
    color: var(--text-light);
    display: flex;
    flex-direction: column;
    padding: 24px;
    position: sticky;
    top: 0;
    height: 100vh;
    z-index: 100;
}

.sidebar__logo {
    margin-bottom: 40px;
}

.sidebar__nav {
    display: flex;
    flex-direction: column;
    gap: 8px;
    flex-grow: 1;
}

.sidebar__link {
    color: #94a3b8;
    text-decoration: none;
    padding: 12px 16px;
    border-radius: 8px;
    font-weight: 500;
    transition: all 0.2s ease;
}

.sidebar__link:hover, 
.sidebar__link--active {
    background-color: rgba(255, 255, 255, 0.1);
    color: var(--white);
}

.sidebar__profile {
    display: flex;
    align-items: center;
    gap: 12px;
    padding-top: 20px;
    border-top: 1px solid #334155;
}

.sidebar__avatar {
    width: 40px;
    height: 40px;
    background-color: var(--primary);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: bold;
}

.sidebar__user-info {
    display: flex;
    flex-direction: column;
}

.sidebar__user-name {
    font-weight: 600;
    font-size: 14px;
}

.sidebar__user-role {
    font-size: 12px;
    color: var(--text-muted);
}

/* Main content wrapper */
.main-content {
    padding: 30px;
    display: flex;
    flex-direction: column;
    gap: 30px;
}

/* ========================================================
   2. TOP HEADER
   ======================================================== */
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: var(--white);
    padding: 20px 30px;
    border-radius: 12px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05);
}

.header__title {
    font-size: 24px;
    font-weight: 700;
}

.header__actions {
    display: flex;
    align-items: center;
    gap: 20px;
}

.header__search {
    padding: 10px 16px;
    border: 1px solid var(--border-color);
    border-radius: 8px;
    outline: none;
    width: 200px;
    transition: width 0.3s ease;
}

.header__search:focus {
    width: 260px;
    border-color: var(--primary);
}

.header__notifications {
    background: none;
    border: none;
    font-size: 20px;
    cursor: pointer;
    position: relative;
}

.header__badge {
    position: absolute;
    top: -5px;
    right: -5px;
    background-color: var(--danger);
    color: var(--white);
    font-size: 10px;
    padding: 2px 6px;
    border-radius: 10px;
    font-weight: bold;
}

/* ========================================================
   3. STATS KARTALAR
   ======================================================== */
.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}

.stat-card {
    background-color: var(--white);
    padding: 24px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    gap: 20px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05);
}

.stat-card__icon {
    font-size: 28px;
    background-color: #f1f5f9;
    padding: 12px;
    border-radius: 10px;
}

.stat-card__details {
    display: flex;
    flex-direction: column;
}

.stat-card__title {
    font-size: 14px;
    color: var(--text-muted);
    font-weight: 500;
}

.stat-card__value {
    font-size: 22px;
    font-weight: 700;
    margin-top: 4px;
}

/* ========================================================
   4. DATA TABLE & STATUS BADGE
   ======================================================== */
.table-container {
    background-color: var(--white);
    padding: 24px;
    border-radius: 12px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05);
}

.table-container__title {
    margin-bottom: 20px;
    font-size: 18px;
}

.table-responsive {
    overflow-x: auto;
}

.data-table {
    width: 100%;
    border-collapse: collapse;
    text-align: left;
}

.data-table th, 
.data-table td {
    padding: 16px;
    border-bottom: 1px solid var(--border-color);
}

.data-table th {
    background-color: #f8fafc;
    color: var(--text-muted);
    font-size: 13px;
    text-transform: uppercase;
    font-weight: 600;
}

.data-table tbody tr:hover {
    background-color: #f8fafc;
}

/* Status Badges */
.status-badge {
    padding: 6px 12px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: 600;
    display: inline-block;
}

.status-badge--success {
    background-color: var(--success-bg);
    color: var(--success);
}

.status-badge--pending {
    background-color: var(--pending-bg);
    color: var(--pending);
}

.status-badge--danger {
    background-color: var(--danger-bg);
    color: var(--danger);
}

/* ========================================================
   6. RESPONSIVE — MOBILGACHA YIQILADIGAN SIDEBAR
   ======================================================== */
@media (max-width: 992px) {
    .dashboard {
        grid-template-columns: 1fr; /* Sidebar alohida ustun bo'lmaydi */
    }

    .sidebar {
        position: relative;
        height: auto;
        width: 100%;
        padding: 16px 20px;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }

    .sidebar__logo {
        margin-bottom: 0;
    }

    .sidebar__nav {
        flex-direction: row;
        gap: 5px;
        flex-grow: 0;
    }

    .sidebar__link {
        padding: 8px 12px;
        font-size: 13px;
    }

    .sidebar__profile {
        border-top: none;
        padding-top: 0;
    }

    .sidebar__user-info {
        display: none; /* Mobil ekranda joy tejash uchun */
    }
}

@media (max-width: 576px) {
    .sidebar {
        flex-direction: column;
        gap: 15px;
    }

    .sidebar__nav {
        flex-wrap: wrap;
        justify-content: center;
    }

    .header {
        flex-direction: column;
        align-items: flex-start;
        gap: 15px;
    }

    .header__actions {
        width: 100%;
        justify-content: space-between;
    }

    .header__search {
        width: 100%;
    }
    
    .header__search:focus {
        width: 100%;
    }
}
