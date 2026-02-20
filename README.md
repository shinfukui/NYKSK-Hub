<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>New York Kenshinkai Hub</title>
<link href="https://fonts.googleapis.com/css2?family=Shippori+Mincho:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #1a1410;
    --paper: #f5f0e8;
    --red: #c0392b;
    --red-dark: #922b21;
    --gold: #00a0df; /* Charles Schwab light blue */
    --gold-light: #e6f7ff; /* Light blue tint */
    --gray: #7a7060;
    --gray-light: #e8e2d6;
    --white: #fdfaf5;
    --shadow: 0 4px 24px rgba(0,160,223,0.12);
    --shadow-lg: 0 12px 48px rgba(0,160,223,0.18);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  /* Hide GitHub Pages default header */
  body > h1:first-child,
  body > header:first-child,
  #header,
  .page-header,
  body > h1:first-of-type {
    display: none !important;
    visibility: hidden !important;
    height: 0 !important;
    margin: 0 !important;
    padding: 0 !important;
  }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--paper);
    color: var(--ink);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Background texture */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%231a1410' fill-opacity='0.025'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
  }

  /* HEADER */
  header {
    position: relative;
    background: #00a0df; /* Schwab light blue */
    color: var(--white);
    padding: 0;
    overflow: hidden;
    z-index: 10;
  }

  .header-accent {
    position: absolute;
    top: 0; left: 0;
    width: 6px;
    height: 100%;
    background: var(--red);
  }

  .header-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 20px 40px 20px 52px;
    flex-wrap: wrap;
    gap: 12px;
  }

  .dojo-brand {
    display: flex;
    align-items: center;
    gap: 18px;
  }

  .dojo-mon {
    width: 52px;
    height: 52px;
    position: relative;
    flex-shrink: 0;
    background: var(--gold); /* Light blue background */
    border-radius: 50%; /* Make it circular */
    padding: 4px;
  }

  .dojo-mon svg { width: 100%; height: 100%; }

  .dojo-title h1 {
    font-family: 'Shippori Mincho', serif;
    font-size: 22px;
    font-weight: 700;
    letter-spacing: 0.04em;
    color: var(--paper);
    line-height: 1.1;
  }

  .dojo-title p {
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gold);
    margin-top: 2px;
  }

  .header-actions {
    display: flex;
    gap: 10px;
    align-items: center;
    flex-wrap: wrap;
  }

  /* ROLE SWITCHER */
  .role-badge {
    display: flex;
    align-items: center;
    gap: 8px;
    background: rgba(255,255,255,0.08);
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 100px;
    padding: 6px 14px 6px 8px;
    font-size: 12px;
    color: var(--paper);
    cursor: pointer;
    transition: all 0.2s;
  }
  .role-badge:hover { background: rgba(255,255,255,0.14); }
  .role-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--gold); }
  .role-dot.admin { background: var(--red); }

  .btn-primary {
    background: var(--red);
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 6px;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    cursor: pointer;
    letter-spacing: 0.02em;
    transition: all 0.2s;
    display: flex;
    align-items: center;
    gap: 7px;
  }
  .btn-primary:hover { background: var(--red-dark); transform: translateY(-1px); box-shadow: 0 4px 12px rgba(192,57,43,0.4); }

  /* MAIN */
  main {
    position: relative;
    z-index: 1;
    max-width: 1400px;
    margin: 0 auto;
    padding: 32px 24px 60px;
  }

  /* TWO-COLUMN LAYOUT */
  .main-content-wrapper {
    display: grid;
    grid-template-columns: 3fr 1fr;
    gap: 24px;
    align-items: start;
  }

  .main-content {
    min-width: 0; /* Prevents grid blowout */
  }

  .sidebar {
    position: sticky;
    top: 24px;
    max-height: calc(100vh - 48px);
    overflow-y: auto;
  }

  /* FILTERS & SEARCH */
  .controls {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 28px;
    flex-wrap: wrap;
  }

  .search-box {
    flex: 1;
    min-width: 200px;
    position: relative;
  }

  .search-box input {
    width: 100%;
    padding: 10px 16px 10px 40px;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    background: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    color: var(--ink);
    outline: none;
    transition: border-color 0.2s;
  }
  .search-box input:focus { border-color: var(--red); }
  .search-icon {
    position: absolute;
    left: 13px;
    top: 50%;
    transform: translateY(-50%);
    color: var(--gray);
    font-size: 15px;
  }

  .filter-tabs {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }

  .filter-tab {
    padding: 8px 14px;
    border-radius: 100px;
    border: 1.5px solid var(--gray-light);
    background: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
    font-weight: 500;
    color: var(--gray);
    cursor: pointer;
    transition: all 0.18s;
    letter-spacing: 0.02em;
    display: flex;
    align-items: center;
    gap: 5px;
  }
  .filter-tab:hover { border-color: var(--ink); color: var(--ink); }
  .filter-tab.active { background: var(--ink); border-color: var(--ink); color: var(--paper); }
  .filter-tab .tab-dot { width: 7px; height: 7px; border-radius: 50%; }

  /* VIEW TOGGLE */
  .view-toggle {
    display: flex;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    overflow: hidden;
    background: var(--white);
  }
  .view-btn {
    padding: 9px 13px;
    border: none;
    background: transparent;
    cursor: pointer;
    color: var(--gray);
    font-size: 15px;
    transition: all 0.18s;
    border-right: 1.5px solid var(--gray-light);
  }
  .view-btn:last-child { border-right: none; }
  .view-btn.active { background: var(--ink); color: var(--paper); }
  .view-btn:hover:not(.active) { background: var(--gray-light); }

  /* SECTION HEADER */
  .section-header {
    display: flex;
    align-items: baseline;
    gap: 12px;
    margin-bottom: 18px;
  }
  .section-title {
    font-family: 'Shippori Mincho', serif;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gray);
  }
  .section-line {
    flex: 1;
    height: 1px;
    background: var(--gray-light);
  }
  .event-count {
    font-size: 12px;
    color: var(--gray);
  }

  /* EVENT GRID */
  .events-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 18px;
    animation: fadeUp 0.4s ease both;
  }

  .events-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
    animation: fadeUp 0.4s ease both;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* EVENT CARD */
  .event-card {
    background: var(--white);
    border-radius: 12px;
    border: 1.5px solid var(--gray-light);
    overflow: hidden;
    transition: all 0.22s;
    cursor: pointer;
    position: relative;
    display: flex;
    flex-direction: column;
  }
  .event-card:hover {
    border-color: var(--ink);
    box-shadow: var(--shadow-lg);
    transform: translateY(-3px);
  }

  .card-stripe {
    height: 4px;
    width: 100%;
    flex-shrink: 0;
  }

  .card-body {
    padding: 18px 20px;
    flex: 1;
    display: flex;
    flex-direction: column;
  }

  .card-meta {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 10px;
  }

  .event-type-badge {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    padding: 3px 10px;
    border-radius: 100px;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .card-date-chip {
    display: flex;
    flex-direction: column;
    align-items: center;
    background: var(--ink);
    color: var(--paper);
    border-radius: 8px;
    padding: 6px 10px;
    min-width: 44px;
    text-align: center;
  }
  .chip-month { font-size: 9px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--gold); }
  .chip-day { font-family: 'Shippori Mincho', serif; font-size: 22px; font-weight: 700; line-height: 1; }

  .card-title {
    font-family: 'Shippori Mincho', serif;
    font-size: 17px;
    font-weight: 700;
    color: var(--ink);
    line-height: 1.3;
    margin-bottom: 6px;
  }

  .card-desc {
    font-size: 13px;
    color: var(--gray);
    line-height: 1.55;
    margin-bottom: 14px;
    flex: 1;
  }

  .card-details {
    display: flex;
    flex-direction: column;
    gap: 5px;
    margin-bottom: 14px;
    padding: 12px;
    background: rgba(26,20,16,0.03);
    border-radius: 8px;
  }

  .detail-row {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 12px;
    color: var(--gray);
  }
  .detail-icon { font-size: 13px; width: 16px; text-align: center; }
  .detail-val { color: var(--ink); font-weight: 500; }

  .card-footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 8px;
  }

  .participants-row {
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .avatar-stack {
    display: flex;
  }
  .avatar {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    border: 2px solid var(--white);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 9px;
    font-weight: 700;
    color: white;
    margin-left: -6px;
    flex-shrink: 0;
  }
  .avatar:first-child { margin-left: 0; }
  .avatar-count {
    font-size: 11px;
    color: var(--gray);
    margin-left: 4px;
  }

  .doc-pills {
    display: flex;
    gap: 5px;
    flex-wrap: wrap;
  }

  .doc-pill {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    padding: 3px 8px;
    border-radius: 4px;
    background: var(--gold-light);
    color: var(--ink);
    font-size: 10px;
    font-weight: 500;
    text-decoration: none;
    transition: background 0.15s;
    cursor: pointer;
  }
  .doc-pill:hover { background: var(--gold); }

  .register-btn {
    padding: 7px 14px;
    border-radius: 6px;
    border: 1.5px solid var(--red);
    background: transparent;
    color: var(--red);
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.18s;
    letter-spacing: 0.02em;
  }
  .register-btn:hover { background: var(--red); color: white; }
  .register-btn.registered { background: var(--red); color: white; border-color: var(--red); }
  .register-btn.registered:hover { background: var(--red-dark); border-color: var(--red-dark); }

  /* LIST VIEW CARD */
  .event-card.list-mode {
    flex-direction: row;
    align-items: stretch;
  }
  .event-card.list-mode .card-stripe { width: 5px; height: auto; flex-shrink: 0; }
  .event-card.list-mode .card-body {
    flex-direction: row;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
    padding: 14px 20px;
  }
  .event-card.list-mode .card-date-chip { min-width: 50px; }
  .event-card.list-mode .list-main { flex: 1; min-width: 180px; }
  .event-card.list-mode .list-main .card-title { font-size: 15px; margin-bottom: 2px; }
  .event-card.list-mode .list-main .card-desc { font-size: 12px; margin-bottom: 0; }
  .event-card.list-mode .card-details {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 8px 16px;
    background: transparent;
    padding: 0;
    margin-bottom: 0;
    min-width: 220px;
  }
  .event-card.list-mode .card-footer { flex-shrink: 0; }

  /* TYPE COLORS */
  .type-manhattan { color: #2d6a4f; background: #d8f3dc; }
  .stripe-manhattan { background: #2d6a4f; }

  .type-njkids { color: #c87a07; background: #fef5e7; }
  .stripe-njkids { background: #f39c12; }

  .type-tournament { color: #922b21; background: #fadbd8; }
  .stripe-tournament { background: #922b21; }

  .type-seminar { color: #1a5276; background: #d6eaf8; }
  .stripe-seminar { background: #1a5276; }

  .type-joint { color: #7d6608; background: #fef9e7; }
  .stripe-joint { background: #c9a84c; }

  .type-exam { color: #4a235a; background: #e8daef; }
  .stripe-exam { background: #8e44ad; }

  .type-other { color: #4a235a; background: #e8daef; }
  .stripe-other { background: #7d3c98; }

  /* AVATAR COLORS */
  .av1 { background: #c0392b; }
  .av2 { background: #2980b9; }
  .av3 { background: #27ae60; }
  .av4 { background: #8e44ad; }
  .av5 { background: #e67e22; }
  .av6 { background: #16a085; }

  /* MODAL */
  .modal-overlay {
    position: fixed;
    inset: 0;
    background: rgba(26,20,16,0.55);
    z-index: 1000;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;
    backdrop-filter: blur(3px);
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.25s;
  }
  .modal-overlay.open { opacity: 1; pointer-events: all; }

  .modal {
    background: var(--white);
    border-radius: 16px;
    max-width: 580px;
    width: 100%;
    max-height: 90vh;
    overflow-y: auto;
    box-shadow: var(--shadow-lg);
    transform: translateY(20px) scale(0.97);
    transition: transform 0.25s ease;
  }
  .modal-overlay.open .modal { transform: translateY(0) scale(1); }

  .modal-header {
    padding: 24px 28px 0;
    position: relative;
  }

  .modal-close {
    position: absolute;
    top: 18px; right: 20px;
    background: var(--gray-light);
    border: none;
    border-radius: 50%;
    width: 30px; height: 30px;
    font-size: 16px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--ink);
    transition: background 0.15s;
  }
  .modal-close:hover { background: var(--red); color: white; }

  .modal h2 {
    font-family: 'Shippori Mincho', serif;
    font-size: 22px;
    font-weight: 700;
    margin-bottom: 6px;
    padding-right: 40px;
  }

  .modal-body {
    padding: 20px 28px 28px;
  }

  .form-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }
  .form-col-full { grid-column: 1 / -1; }

  .form-group label {
    display: block;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gray);
    margin-bottom: 5px;
  }

  .form-group input,
  .form-group select,
  .form-group textarea {
    width: 100%;
    padding: 10px 13px;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    background: var(--paper);
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    color: var(--ink);
    outline: none;
    transition: border-color 0.2s;
    appearance: none;
  }
  .form-group input:focus,
  .form-group select:focus,
  .form-group textarea:focus { border-color: var(--red); }

  .form-group textarea { min-height: 80px; resize: vertical; }

  .form-group select {
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%237a7060' d='M6 8L1 3h10z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
    padding-right: 32px;
  }

  .doc-input-row {
    display: flex;
    gap: 8px;
    margin-top: 6px;
  }
  .doc-input-row input { flex: 1; }
  .doc-input-row button {
    padding: 10px 14px;
    border: 1.5px dashed var(--gray-light);
    border-radius: 8px;
    background: transparent;
    color: var(--gray);
    font-size: 18px;
    cursor: pointer;
    transition: all 0.18s;
    white-space: nowrap;
  }
  .doc-input-row button:hover { border-color: var(--red); color: var(--red); background: #fff5f5; }

  .doc-list-preview { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 8px; }
  .doc-rm { font-size: 10px; margin-left: 4px; cursor: pointer; opacity: 0.6; }
  .doc-rm:hover { opacity: 1; color: var(--red); }

  .form-actions {
    display: flex;
    justify-content: flex-end;
    gap: 10px;
    margin-top: 20px;
  }

  .btn-ghost {
    padding: 10px 18px;
    border: 1.5px solid var(--gray-light);
    border-radius: 6px;
    background: transparent;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    color: var(--gray);
    cursor: pointer;
    transition: all 0.18s;
  }
  .btn-ghost:hover { border-color: var(--ink); color: var(--ink); }

  /* TOAST */
  .toast {
    position: fixed;
    bottom: 28px;
    right: 28px;
    background: var(--ink);
    color: var(--paper);
    padding: 12px 20px;
    border-radius: 10px;
    font-size: 13px;
    font-weight: 500;
    box-shadow: var(--shadow-lg);
    z-index: 9999;
    transform: translateY(20px);
    opacity: 0;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    gap: 8px;
    border-left: 4px solid var(--red);
  }
  .toast.show { transform: translateY(0); opacity: 1; }

  /* EMPTY STATE */
  .empty-state {
    text-align: center;
    padding: 60px 20px;
    color: var(--gray);
  }
  .empty-state .empty-icon { font-size: 48px; margin-bottom: 14px; opacity: 0.5; }
  .empty-state h3 { font-family: 'Shippori Mincho', serif; font-size: 18px; color: var(--ink); margin-bottom: 6px; }
  .empty-state p { font-size: 13px; }

  /* UPCOMING STRIP */
  .upcoming-strip {
    background: var(--ink);
    border-radius: 12px;
    padding: 16px 24px;
    margin-bottom: 28px;
    display: flex;
    gap: 0;
    overflow-x: auto;
    scrollbar-width: none;
    position: relative;
  }
  .upcoming-strip::-webkit-scrollbar { display: none; }
  .upcoming-strip::before {
    content: 'UPCOMING';
    position: absolute;
    top: 14px; left: 24px;
    font-size: 9px;
    letter-spacing: 0.2em;
    color: var(--gold);
    font-weight: 600;
  }

  .up-item {
    flex-shrink: 0;
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 22px 20px 8px;
    border-right: 1px solid rgba(255,255,255,0.08);
    cursor: pointer;
    transition: background 0.15s;
    border-radius: 8px;
    min-width: 180px;
  }
  .up-item:last-child { border-right: none; }
  .up-item:hover { background: rgba(255,255,255,0.06); }

  .up-date {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-width: 36px;
  }
  .up-month { font-size: 9px; letter-spacing: 0.1em; color: var(--gold); text-transform: uppercase; }
  .up-day { font-family: 'Shippori Mincho', serif; font-size: 24px; font-weight: 800; color: var(--paper); line-height: 1; }

  .up-info { flex: 1; }
  .up-name { font-size: 12px; font-weight: 600; color: var(--paper); line-height: 1.3; }
  .up-type { font-size: 10px; color: var(--gray); margin-top: 2px; text-transform: uppercase; letter-spacing: 0.06em; }

  /* ── LOGIN SCREEN ───────────────────────────────────────────────────────── */
  .login-overlay {
    position: fixed;
    inset: 0;
    background: #00a0df; /* Schwab light blue */
    z-index: 9000;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 24px;
    transition: opacity 0.5s ease;
  }
  .login-overlay.hidden { opacity: 0; pointer-events: none; }

  .login-box {
    background: var(--white);
    border-radius: 20px;
    padding: 44px 40px 36px;
    max-width: 380px;
    width: 100%;
    text-align: center;
    box-shadow: 0 32px 80px rgba(0,0,0,0.4);
    position: relative;
    overflow: hidden;
  }
  .login-box::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 5px;
    background: var(--red);
  }

  .login-mon {
    width: 64px; height: 64px;
    margin: 0 auto 20px;
    background: var(--gold); /* Light blue background */
    border-radius: 50%; /* Make it circular */
    padding: 6px;
  }
  .login-mon svg { width: 100%; height: 100%; }

  .login-box h2 {
    font-family: 'Shippori Mincho', serif;
    font-size: 24px;
    font-weight: 800;
    color: var(--ink);
    margin-bottom: 4px;
  }
  .login-box p {
    font-size: 13px;
    color: var(--gray);
    margin-bottom: 28px;
    line-height: 1.5;
  }

  .login-name-row {
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin-bottom: 16px;
    text-align: left;
  }
  .login-name-row label {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gray);
    display: block;
    margin-bottom: 5px;
  }
  .login-name-row input {
    width: 100%;
    padding: 11px 14px;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    color: var(--ink);
    background: var(--paper);
    outline: none;
    transition: border-color 0.2s;
  }
  .login-name-row input:focus { border-color: var(--red); }

  .passcode-dots {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin: 8px 0 20px;
  }
  .passcode-dot {
    width: 14px; height: 14px;
    border-radius: 50%;
    border: 2px solid var(--gray-light);
    background: transparent;
    transition: all 0.2s;
  }
  .passcode-dot.filled { background: var(--red); border-color: var(--red); }
  .passcode-dot.error { background: #e74c3c; border-color: #e74c3c; animation: shake 0.4s ease; }

  @keyframes shake {
    0%,100% { transform: translateX(0); }
    20%,60% { transform: translateX(-4px); }
    40%,80% { transform: translateX(4px); }
  }

  .pin-pad {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    margin-bottom: 16px;
  }
  .pin-btn {
    aspect-ratio: 1;
    border-radius: 12px;
    border: 1.5px solid var(--gold);
    background: var(--gold); /* Light blue background */
    font-family: 'Shippori Mincho', serif;
    font-size: 20px;
    font-weight: 700;
    color: var(--white); /* White text */
    cursor: pointer;
    transition: all 0.15s;
    display: flex; align-items: center; justify-content: center;
  }
  .pin-btn:hover { background: #0088c7; color: var(--white); border-color: #0088c7; transform: scale(1.04); } /* Darker blue on hover */
  .pin-btn:active { transform: scale(0.96); }
  .pin-btn.del { font-size: 16px; background: var(--paper); color: var(--gray); border-color: var(--gray-light); }
  .pin-btn.del:hover { background: #fadbd8; color: var(--red); border-color: var(--red); }

  .login-hint {
    font-size: 11px;
    color: var(--gray);
    margin-top: 10px;
  }
  .login-hint strong { color: var(--ink); }

  .login-error {
    font-size: 12px;
    color: var(--red);
    min-height: 18px;
    margin-bottom: 8px;
  }

  /* ── TRUSTED MEMBER PANEL ────────────────────────────────────────────────── */
  .admin-panel-btn {
    background: rgba(255,255,255,0.08);
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 6px;
    padding: 8px 12px;
    color: var(--paper);
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
    cursor: pointer;
    transition: all 0.2s;
    display: flex; align-items: center; gap: 6px;
  }
  .admin-panel-btn:hover { background: rgba(255,255,255,0.14); }

  .members-panel {
    background: var(--white);
    border-radius: 12px;
    border: 1.5px solid var(--gray-light);
    margin-bottom: 24px;
    overflow: hidden;
    animation: fadeUp 0.3s ease both;
  }
  .members-panel-header {
    background: var(--ink);
    padding: 14px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .members-panel-header h3 {
    font-family: 'Shippori Mincho', serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--paper);
  }
  .members-panel-header span {
    font-size: 11px;
    color: var(--gold);
    letter-spacing: 0.08em;
  }

  .members-list {
    padding: 8px 0;
    max-height: 280px;
    overflow-y: auto;
  }

  .member-row {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 10px 20px;
    transition: background 0.15s;
    cursor: default;
  }
  .member-row:hover { background: var(--paper); }

  .member-avatar {
    width: 34px; height: 34px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 12px;
    font-weight: 700;
    color: white;
    flex-shrink: 0;
  }

  .member-info { flex: 1; }
  .member-name { font-size: 13px; font-weight: 600; color: var(--ink); }
  .member-since { font-size: 11px; color: var(--gray); }

  .role-toggle {
    display: flex;
    border: 1.5px solid var(--gray-light);
    border-radius: 6px;
    overflow: hidden;
    flex-shrink: 0;
  }
  .role-opt {
    padding: 5px 10px;
    font-size: 11px;
    font-weight: 500;
    cursor: pointer;
    border: none;
    background: transparent;
    color: var(--gray);
    font-family: 'DM Sans', sans-serif;
    transition: all 0.15s;
    white-space: nowrap;
  }
  .role-opt.active-member { background: #d8f3dc; color: #1b4332; }
  .role-opt.active-trusted { background: var(--gold-light); color: #6e5205; }
  .role-opt.active-admin { background: #fadbd8; color: var(--red-dark); }

  .no-members {
    text-align: center;
    padding: 24px;
    font-size: 13px;
    color: var(--gray);
  }

  /* ── IMPROVED DOC ATTACHMENT ─────────────────────────────────────────────── */
  .doc-tabs {
    display: flex;
    gap: 0;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 8px;
  }
  .doc-tab-btn {
    flex: 1;
    padding: 8px;
    border: none;
    background: var(--paper);
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
    font-weight: 500;
    color: var(--gray);
    cursor: pointer;
    transition: all 0.15s;
    border-right: 1.5px solid var(--gray-light);
  }
  .doc-tab-btn:last-child { border-right: none; }
  .doc-tab-btn.active { background: var(--ink); color: var(--paper); }

  .doc-attach-row {
    display: flex;
    gap: 8px;
    margin-bottom: 4px;
  }
  .doc-attach-row input { flex: 1; }

  .doc-pill-link {
    background: #d6eaf8;
    color: #1a3a5c;
  }
  .doc-pill-link:hover { background: #aed6f1; }
  .doc-pill-file {
    background: var(--gold-light);
    color: #6e5205;
  }
  .doc-pill-file:hover { background: var(--gold); }

  /* ── MESSAGE BOARD ────────────────────────────────────────────────────────── */
  .message-board {
    background: var(--white);
    border-radius: 12px;
    border: 1.5px solid var(--gray-light);
    margin-bottom: 24px;
    overflow: hidden;
    animation: fadeUp 0.3s ease both;
  }
  .message-board-header {
    background: var(--ink);
    padding: 14px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .message-board-header h3 {
    font-family: 'Shippori Mincho', serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--paper);
  }

  .message-form {
    padding: 16px 20px;
    border-bottom: 1.5px solid var(--gray-light);
    background: var(--paper);
  }
  .message-form textarea {
    width: 100%;
    padding: 10px 13px;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    background: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    color: var(--ink);
    min-height: 60px;
    resize: vertical;
    margin-bottom: 8px;
  }
  .message-form textarea:focus { border-color: var(--red); outline: none; }
  
  .message-form-actions {
    display: flex;
    gap: 8px;
    align-items: center;
    flex-wrap: wrap;
  }
  .message-form-actions input {
    flex: 1;
    min-width: 200px;
    padding: 8px 12px;
    border: 1.5px solid var(--gray-light);
    border-radius: 6px;
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
  }
  .message-form-actions input:focus { border-color: var(--red); outline: none; }

  .messages-list {
    padding: 8px 0;
    max-height: 500px;
    overflow-y: auto;
  }

  .message-item {
    padding: 14px 20px;
    border-bottom: 1px solid var(--gray-light);
    transition: background 0.15s;
  }
  .message-item:last-child { border-bottom: none; }
  .message-item:hover { background: var(--paper); }

  .message-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 8px;
  }
  .message-avatar {
    width: 32px; height: 32px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 11px;
    font-weight: 700;
    color: white;
    flex-shrink: 0;
  }
  .message-author {
    font-size: 13px;
    font-weight: 600;
    color: var(--ink);
  }
  .message-time {
    font-size: 11px;
    color: var(--gray);
    margin-left: auto;
  }
  .message-text {
    font-size: 13px;
    color: var(--ink);
    line-height: 1.5;
    margin-bottom: 8px;
    white-space: pre-wrap;
    word-wrap: break-word;
  }
  .message-link {
    display: inline-block;
    font-size: 12px;
    color: #1a5276;
    text-decoration: none;
    padding: 4px 10px;
    background: #d6eaf8;
    border-radius: 4px;
    margin-top: 4px;
    transition: background 0.15s;
  }
  .message-link:hover { background: #aed6f1; }
  .message-image {
    max-width: 100%;
    max-height: 300px;
    border-radius: 8px;
    margin-top: 8px;
    cursor: pointer;
  }
  .message-delete {
    font-size: 11px;
    color: var(--gray);
    cursor: pointer;
    padding: 2px 6px;
    border-radius: 3px;
    transition: all 0.15s;
    margin-left: 8px;
  }
  .message-delete:hover { background: #fadbd8; color: var(--red); }

  .no-messages {
    text-align: center;
    padding: 32px;
    color: var(--gray);
    font-size: 13px;
  }

  /* ── RESPONSIVE ──────────────────────────────────────────────────────────── */
  @media (max-width: 640px) {
    .header-inner { padding: 16px 20px 16px 30px; }
    main { padding: 20px 14px 40px; }
    .form-grid { grid-template-columns: 1fr; }
    .events-grid { grid-template-columns: 1fr; }
    .event-card.list-mode { flex-direction: column; }
    .event-card.list-mode .card-stripe { width: 100%; height: 4px; }
    .event-card.list-mode .card-body { flex-direction: column; align-items: flex-start; }
    
    /* Stack layout on mobile */
    .main-content-wrapper {
      grid-template-columns: 1fr;
      gap: 16px;
    }
    .sidebar {
      position: static;
      max-height: none;
    }
  }

  /* ── CALENDAR VIEW ─────────────────────────────────────────────────────── */
  .calendar-wrap {
    animation: fadeUp 0.35s ease both;
  }

  .cal-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 20px;
    gap: 12px;
  }

  .cal-month-label {
    font-family: 'Shippori Mincho', serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--ink);
    letter-spacing: 0.02em;
    flex: 1;
    text-align: center;
  }

  .cal-nav-btn {
    width: 36px; height: 36px;
    border-radius: 50%;
    border: 1.5px solid var(--gray-light);
    background: var(--white);
    color: var(--ink);
    font-size: 16px;
    cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    transition: all 0.18s;
    flex-shrink: 0;
  }
  .cal-nav-btn:hover { background: var(--ink); color: var(--paper); border-color: var(--ink); }

  .cal-today-btn {
    padding: 7px 14px;
    border-radius: 6px;
    border: 1.5px solid var(--gray-light);
    background: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
    font-weight: 500;
    color: var(--gray);
    cursor: pointer;
    transition: all 0.18s;
  }
  .cal-today-btn:hover { border-color: var(--ink); color: var(--ink); }

  .cal-grid {
    background: var(--white);
    border-radius: 14px;
    border: 1.5px solid var(--gray-light);
    overflow: hidden;
    box-shadow: var(--shadow);
  }

  .cal-dow-row {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    border-bottom: 1.5px solid var(--gray-light);
    background: var(--ink);
  }

  .cal-dow {
    text-align: center;
    padding: 10px 4px;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gold);
  }

  .cal-days {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
  }

  .cal-cell {
    min-height: 108px;
    border-right: 1px solid var(--gray-light);
    border-bottom: 1px solid var(--gray-light);
    padding: 8px 6px 6px;
    position: relative;
    transition: background 0.15s;
    vertical-align: top;
    cursor: default;
  }
  .cal-cell:nth-child(7n) { border-right: none; }
  .cal-cell.other-month { background: rgba(26,20,16,0.02); }
  .cal-cell.other-month .cal-day-num { color: var(--gray-light); }
  .cal-cell.today { background: #fff8f7; }
  .cal-cell.has-events { cursor: pointer; }
  .cal-cell.has-events:hover { background: #fdfaf5; }

  .cal-day-num {
    font-family: 'Shippori Mincho', serif;
    font-size: 14px;
    font-weight: 600;
    color: var(--gray);
    margin-bottom: 5px;
    display: flex;
    align-items: center;
    gap: 4px;
  }

  .today-pip {
    width: 20px; height: 20px;
    border-radius: 50%;
    background: var(--red);
    color: white;
    font-size: 11px;
    font-weight: 700;
    display: flex; align-items: center; justify-content: center;
    font-family: 'DM Sans', sans-serif;
  }

  .cal-event-pill {
    display: block;
    padding: 2px 6px;
    border-radius: 4px;
    font-size: 10px;
    font-weight: 500;
    margin-bottom: 3px;
    cursor: pointer;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    transition: opacity 0.15s, transform 0.15s;
    line-height: 1.6;
  }
  .cal-event-pill:hover { opacity: 0.85; transform: translateX(1px); }

  .cal-more {
    font-size: 10px;
    color: var(--gray);
    cursor: pointer;
    padding: 1px 4px;
    border-radius: 3px;
    transition: background 0.15s;
  }
  .cal-more:hover { background: var(--gray-light); color: var(--ink); }

  /* Day detail popover */
  .day-popover {
    position: fixed;
    z-index: 500;
    background: var(--white);
    border-radius: 12px;
    box-shadow: var(--shadow-lg);
    border: 1.5px solid var(--gray-light);
    width: 280px;
    padding: 16px;
    animation: fadeUp 0.2s ease both;
    pointer-events: all;
  }

  .popover-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 12px;
  }
  .popover-date {
    font-family: 'Shippori Mincho', serif;
    font-size: 15px;
    font-weight: 700;
  }
  .popover-close {
    background: none; border: none; font-size: 16px;
    cursor: pointer; color: var(--gray); padding: 2px 6px;
    border-radius: 4px; transition: background 0.15s;
  }
  .popover-close:hover { background: var(--gray-light); }

  .popover-event {
    display: flex;
    gap: 10px;
    padding: 9px 0;
    border-bottom: 1px solid var(--gray-light);
    cursor: pointer;
    transition: background 0.15s;
    border-radius: 6px;
    padding: 8px;
    margin: 0 -8px;
  }
  .popover-event:last-child { border-bottom: none; }
  .popover-event:hover { background: var(--paper); }

  .popover-dot {
    width: 10px; height: 10px;
    border-radius: 50%;
    flex-shrink: 0;
    margin-top: 4px;
  }

  .popover-ev-title {
    font-size: 13px;
    font-weight: 600;
    color: var(--ink);
    line-height: 1.3;
  }
  .popover-ev-sub {
    font-size: 11px;
    color: var(--gray);
    margin-top: 2px;
  }

  /* Pill colors per type */
  .pill-class      { background: #d8f3dc; color: #1b4332; }
  .pill-tournament { background: #fadbd8; color: #7b241c; }
  .pill-seminar    { background: #d6eaf8; color: #1a3a5c; }
  .pill-joint      { background: #fef9e7; color: #6e5205; }
  .pill-other      { background: #e8daef; color: #4a235a; }

  /* PERMISSION NOTICE */
  .perm-notice {
    background: linear-gradient(135deg, #fef9e7, #fdebd0);
    border: 1px solid var(--gold-light);
    border-radius: 8px;
    padding: 10px 14px;
    font-size: 12px;
    color: #7d6608;
    margin-bottom: 18px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
</style>
</head>
<body>

<!-- ══ LOGIN SCREEN ══════════════════════════════════════════════════════════ -->
<div class="login-overlay" id="loginOverlay">
  <div class="login-box">
    <div class="login-mon">
      <img src="data:image/png;base64,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f19fnzokkuG5AKyMMAzffvtt3Uv8XLFY7O3ttRoBVoC4H4iEUqm0Y8cOdUib0dHRzs5Oq15Wnaw/wYzNBdKpWq3+7W9/++67744fP17/mW+++ebHH3989NFHF/6Ztra23/72ty0tLb/5zW9+97vfWZItYfEd4cvP6T8AVoa4H1hlYRju3LlzbGxMKVIln8+PjIyYo00UyPqTbXZ21hgfID1qtdq77747MjIyOzt7s/9uNpt99NFH29ra7r777vXr13v58haVSqWenh7vLnPV3zJdCMByE/cDq6lareZyuUXsRoj1Gvf9999vb29XCiKyFfdqUYINDQ3t3btXHYCUmJub27Rp0xLmy7lcbvv27Q888MD999+vS2MRarXa7t27NTZx1W7o1KlTehGA5SPuB1bN5OTk1q1b1SFVzKwkUsrlckdHhzokVT6fdzIekB7Dw8PLOjI+CIJHHnnk8ccff+ihh/Qm3+yuZ9euXdr8udKJEye2bNmiDsByEPcDqyAMw4GBAdMzUsWRvESNrD/x15yvvvrKw0UgJTZu3LiSk+KDIHjqqacee+wxXf83vv3p6ek5fPiwUrCgWCweOHBAHYAlJ+4HVpqjq1JodHS0UCioA9Eh6082g3EBN7UVUx/4s2HDBsNJftWST1si7vL5/LFjx3QnAEtL3A9Y47K8S1hH8hI1sv7Em56edkAIkB733XdfRI7C6u7ufvzxxzds2GDt90u85cxVcrncRx995K8MsITE/cDKWe6JokSKI3mJJll/4nmdCHBfW3X1lv9nnnnGi1bXVKlUtm/fHpGHNERh3+StRGAJifuBlRCG4c6dO8fGxpQiJbq7uwcHB72XStTI+hPPGFwgbaLT2n9N9Sn/Tz75pFE/P98fvf3223qhqNMpBSwhcT+w7KrVahAEBvikRBAE7733nh0dESTrT7xcLnfy5EkPGoFUWeFDehctm812dXU99thjra2tLtQLtPlzpRMnTmzZskUdgFt0mxIAy6pcLt95552y/pQYGhr66quvZP1E0PDwsKw/2YIgkPUDKRSXASDz8/N9fX0dHR3/+q//un///nK5HIahj6+5ufmrr74aGhpSCjKZzNatW/v7+9UBuEXifmC5hGHY398vX0uJIAguXry4d+9eWRsR1N/f72X5ZMtms1NTU64/ALFw+PBhuf+ChoaGvXv3Xrx4MQgC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 alt="Kenshinkai Logo" style="width:100%;height:100%;object-fit:contain;;filter:invert(1);">
    </div>
    <h2>NY Kenshinkai</h2>
    <p>Enter your name and the dojo passcode<br>to access the event board.</p>

    <div class="login-name-row">
      <div>
        <label>Your Name</label>
        <input type="text" id="loginName" placeholder="e.g. Tanaka Kenji" maxlength="40" autocomplete="off">
      </div>
      <div>
        <label>Passcode</label>
        <div class="passcode-dots" id="passcodeDots">
          <div class="passcode-dot" id="dot0"></div>
          <div class="passcode-dot" id="dot1"></div>
          <div class="passcode-dot" id="dot2"></div>
          <div class="passcode-dot" id="dot3"></div>
        </div>
      </div>
    </div>

    <div class="login-error" id="loginError"></div>

    <div class="pin-pad">
      <button class="pin-btn" onclick="pinPress('1')">1</button>
      <button class="pin-btn" onclick="pinPress('2')">2</button>
      <button class="pin-btn" onclick="pinPress('3')">3</button>
      <button class="pin-btn" onclick="pinPress('4')">4</button>
      <button class="pin-btn" onclick="pinPress('5')">5</button>
      <button class="pin-btn" onclick="pinPress('6')">6</button>
      <button class="pin-btn" onclick="pinPress('7')">7</button>
      <button class="pin-btn" onclick="pinPress('8')">8</button>
      <button class="pin-btn" onclick="pinPress('9')">9</button>
      <button class="pin-btn" onclick="pinPress('0')" style="grid-column:2">0</button>
      <button class="pin-btn del" onclick="pinDelete()" style="grid-column:3">⌫</button>
    </div>

    <p class="login-hint">Enter your registered name and the passcode shared by your dojo admin.</p>
  </div>
</div>

<!-- HEADER -->
<header>
  <div class="header-accent"></div>
  <div class="header-inner">
    <div class="dojo-brand">
      <div class="dojo-mon">
        <img src="data:image/png;base64,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f19fnzokkuG5AKyMMAzffvtt3Uv8XLFY7O3ttRoBVoC4H4iEUqm0Y8cOdUib0dHRzs5Oq15Wnaw/wYzNBdKpWq3+7W9/++67744fP17/mW+++ebHH3989NFHF/6Ztra23/72ty0tLb/5zW9+97vfWZItYfEd4cvP6T8AVoa4H1hlYRju3LlzbGxMKVIln8+PjIyYo00UyPqTbXZ21hgfID1qtdq77747MjIyOzt7s/9uNpt99NFH29ra7r777vXr13v58haVSqWenh7vLnPV3zJdCMByE/cDq6lareZyuUXsRoj1Gvf9999vb29XCiKyFfdqUYINDQ3t3btXHYCUmJub27Rp0xLmy7lcbvv27Q888MD999+vS2MRarXa7t27NTZx1W7o1KlTehGA5SPuB1bN5OTk1q1b1SFVzKwkUsrlckdHhzokVT6fdzIekB7Dw8PLOjI+CIJHHnnk8ccff+ihh/Qm3+yuZ9euXdr8udKJEye2bNmiDsByEPcDqyAMw4GBAdMzUsWRvESNrD/x15yvvvrKw0UgJTZu3LiSk+KDIHjqqacee+wxXf83vv3p6ek5fPiwUrCgWCweOHBAHYAlJ+4HVpqjq1JodHS0UCioA9Eh6082g3EBN7UVUx/4s2HDBsNJftWST1si7vL5/LFjx3QnAEtL3A9Y47K8S1hH8hI1sv7Em56edkAIkB733XdfRI7C6u7ufvzxxzds2GDt90u85cxVcrncRx995K8MsITE/cDKWe6JokSKI3mJJll/4nmdCHBfW3X1lv9nnnnGi1bXVKlUtm/fHpGHNERh3+StRGAJifuBlRCG4c6dO8fGxpQiJbq7uwcHB72XStTI+hPPGFwgbaLT2n9N9Sn/Tz75pFE/P98fvf3223qhqNMpBSwhcT+w7KrVahAEBvikRBAE7733nh0dESTrT7xcLnfy5EkPGoFUWeFDehctm812dXU99thjra2tLtQLtPlzpRMnTmzZskUdgFt0mxIAy6pcLt95552y/pQYGhr66quvZP1E0PDwsKw/2YIgkPUDKRSXASDz8/N9fX0dHR3/+q//un///nK5HIahj6+5ufmrr74aGhpSCjKZzNatW/v7+9UBuEXifmC5hGHY398vX0uJIAguXry4d+9eWRsR1N/f72X5ZMtms1NTU64/ALFw+PBhuf+ChoaGvXv3Xrx4MQgC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" alt="Kenshinkai Logo" style="width:100%;height:100%;object-fit:contain;filter:invert(1);">
      </div>
      <div class="dojo-title">
        <h1>New York Kenshinkai</h1>
        <p>Events & Schedule Hub</p>
      </div>
    </div>
    <div class="header-actions">
      <div class="role-badge" id="roleBadge" onclick="toggleRole()" title="Switch role">
        <div class="role-dot admin" id="roleDot"></div>
        <span id="roleLabel">Admin</span>
      </div>
      <button class="admin-panel-btn" id="membersBtn" onclick="toggleMembersPanel()" style="display:none">
        👥 Members
      </button>
      <button class="btn-primary" id="addEventBtn" onclick="openModal()">
        ＋ Add Event
      </button>
    </div>
  </div>
</header>

<!-- MAIN -->
<main>

  <!-- MEMBERS PANEL (admin only) - full width above everything -->
  <div class="members-panel" id="membersPanel" style="display:none">
    <div class="members-panel-header">
      <h3>🥋 Dojo Members</h3>
      <div style="display:flex;align-items:center;gap:10px">
        <span id="memberCountBadge"></span>
        <button class="btn-primary" id="addMemberBtn" onclick="openAddMemberModal()" style="display:none;padding:6px 12px;font-size:12px">+ Add Member</button>
      </div>
    </div>
    <div class="members-list" id="membersList"></div>
  </div>

  <!-- TWO-COLUMN LAYOUT: Main content + Sidebar -->
  <div class="main-content-wrapper">
    
    <!-- LEFT: Main content -->
    <div class="main-content">

  <!-- UPCOMING STRIP -->
  <div class="upcoming-strip" id="upcomingStrip"></div>

  <!-- CONTROLS -->
  <div class="controls">
    <div class="search-box">
      <span class="search-icon">⌕</span>
      <input type="text" id="searchInput" placeholder="Search events, venues, notes…" oninput="renderEvents()">
    </div>
    <div class="filter-tabs" id="filterTabs">
      <button class="filter-tab active" data-type="all" onclick="setFilter('all', this)">All</button>
      <button class="filter-tab" data-type="manhattan" onclick="setFilter('manhattan', this)"><span class="tab-dot" style="background:#2d6a4f"></span>Manhattan</button>
      <button class="filter-tab" data-type="njkids" onclick="setFilter('njkids', this)"><span class="tab-dot" style="background:#f39c12"></span>NJ Kids</button>
      <button class="filter-tab" data-type="tournament" onclick="setFilter('tournament', this)"><span class="tab-dot" style="background:#922b21"></span>Tournament</button>
      <button class="filter-tab" data-type="seminar" onclick="setFilter('seminar', this)"><span class="tab-dot" style="background:#1a5276"></span>Seminar</button>
      <button class="filter-tab" data-type="joint" onclick="setFilter('joint', this)"><span class="tab-dot" style="background:#c9a84c"></span>Joint</button>
      <button class="filter-tab" data-type="exam" onclick="setFilter('exam', this)"><span class="tab-dot" style="background:#8e44ad"></span>Exam</button>
      <button class="filter-tab" data-type="other" onclick="setFilter('other', this)"><span class="tab-dot" style="background:#7d3c98"></span>Other</button>
    </div>
    <div class="view-toggle">
      <button class="view-btn active" id="gridViewBtn" onclick="setView('grid')" title="Grid view">⊞</button>
      <button class="view-btn" id="listViewBtn" onclick="setView('list')" title="List view">☰</button>
      <button class="view-btn" id="calViewBtn" onclick="setView('calendar')" title="Calendar view">▦</button>
    </div>
  </div>

  <!-- SECTION HEADER -->
  <div class="section-header">
    <span class="section-title">Events</span>
    <div class="section-line"></div>
    <span class="event-count" id="eventCountLabel"></span>
  </div>

  <!-- EVENTS CONTAINER -->
  <div id="eventsContainer"></div>

    </div><!-- end main-content -->

    <!-- RIGHT: Sidebar -->
    <div class="sidebar">
      
      <!-- MESSAGE BOARD -->
      <div class="message-board" id="messageBoard">
        <div class="message-board-header">
          <h3>💬 Message Board</h3>
          <span style="font-size:11px;color:var(--gold);letter-spacing:0.08em" id="messageCount"></span>
        </div>
        <div class="message-form">
          <textarea id="messageText" placeholder="Share a message, announcement, or question..."></textarea>
          <div class="message-form-actions">
            <input type="url" id="messageLink" placeholder="Paste a link (optional)">
            <input type="url" id="messageImage" placeholder="Paste image URL (optional)">
            <button class="btn-primary" onclick="postMessage()" style="padding:8px 16px;font-size:12px">Post</button>
          </div>
        </div>
        <div class="messages-list" id="messagesList"></div>
      </div>

    </div><!-- end sidebar -->

  </div><!-- end main-content-wrapper -->

</main>

<!-- ADD/EDIT MODAL -->
<div class="modal-overlay" id="modalOverlay">
  <div class="modal">
    <div class="modal-header">
      <h2 id="modalTitle">New Event</h2>
      <button class="modal-close" onclick="closeModal()">✕</button>
    </div>
    <div class="modal-body">
      <div class="perm-notice" id="permNotice">
        🛡️ You're posting as <strong id="permRole">Admin</strong>. This event will be visible to all members.
      </div>
      <div class="form-grid">
        <div class="form-group form-col-full">
          <label>Event Title</label>
          <select id="fTitleSelect" onchange="handleTitleSelect()">
            <option value="">— Select a common title —</option>
            <option value="Regular Manhattan Practice">Regular Manhattan Practice</option>
            <option value="Regular NJ Kids Class">Regular NJ Kids Class</option>
            <option value="Tournament">Tournament</option>
            <option value="Seminar">Seminar</option>
            <option value="Shinsa (Exam)">Shinsa (Exam)</option>
            <option value="CUSTOM">✏️ Custom (type your own)</option>
          </select>
          <input type="text" id="fTitle" placeholder="Enter custom event title" style="margin-top:8px;display:none">
        </div>
        <div class="form-group">
          <label>Type</label>
          <select id="fType">
            <option value="manhattan">Manhattan Practice</option>
            <option value="njkids">NJ Kids Class</option>
            <option value="tournament">Tournament</option>
            <option value="seminar">Seminar</option>
            <option value="joint">Joint Practice</option>
            <option value="exam">Exam</option>
            <option value="other">Other</option>
          </select>
        </div>
        <div class="form-group">
          <label>Date</label>
          <input type="date" id="fDate">
        </div>
        <div class="form-group">
          <label>Time</label>
          <input type="time" id="fTime">
        </div>
        <div class="form-group">
          <label>End Time (optional)</label>
          <input type="time" id="fTimeEnd">
        </div>
        <div class="form-group form-col-full">
          <label>Venue / Location</label>
          <select id="fVenueSelect" onchange="handleVenueSelect()">
            <option value="">— Select a venue —</option>
            <option value="500 8th Ave, New York, NY 10018">500 8th Ave, New York, NY 10018</option>
            <option value="534 Old Bergen Blvd, Palisades Park, NJ 07650">534 Old Bergen Blvd, Palisades Park, NJ 07650</option>
            <option value="CUSTOM">✏️ Custom (type your own)</option>
          </select>
          <input type="text" id="fVenue" placeholder="Enter custom venue" style="margin-top:8px;display:none">
        </div>
        <div class="form-group">
          <label>Floor (optional)</label>
          <select id="fFloor">
            <option value="">— None —</option>
            <option value="3F">3F</option>
            <option value="4F">4F</option>
            <option value="12F">12F</option>
            <option value="OTHER">Other</option>
          </select>
        </div>
        <div class="form-group">
          <label>Custom Floor</label>
          <input type="text" id="fFloorCustom" placeholder="e.g. B1, 5F" style="display:none">
        </div>
        <div class="form-group">
          <label>Cost / Fee</label>
          <input type="text" id="fCost" placeholder="e.g. Free, $25, ¥3000">
        </div>
        <div class="form-group">
          <label>Registration Deadline</label>
          <input type="date" id="fRegDeadline">
        </div>
        <div class="form-group form-col-full">
          <label>Notes / Description</label>
          <textarea id="fNotes" placeholder="Details, requirements, what to bring…"></textarea>
        </div>
        <div class="form-group form-col-full">
          <label>Documents &amp; Links</label>
          <div class="doc-tabs">
            <button class="doc-tab-btn active" id="docTabLink" onclick="switchDocTab('link')">🔗 Paste a Link</button>
            <button class="doc-tab-btn" id="docTabFile" onclick="switchDocTab('file')">📎 Attach File Name</button>
          </div>
          <div id="docLinkRow" class="doc-attach-row">
            <input type="text" id="fDocName" placeholder="Label (e.g. Entry Form)">
            <input type="url" id="fDocUrl" placeholder="https://drive.google.com/…" style="flex:2">
            <button onclick="addDoc()" style="padding:10px 14px;border:1.5px dashed var(--gray-light);border-radius:8px;background:transparent;color:var(--gray);font-size:16px;cursor:pointer;transition:all 0.18s;white-space:nowrap;" onmouseover="this.style.borderColor='var(--red)';this.style.color='var(--red)'" onmouseout="this.style.borderColor='var(--gray-light)';this.style.color='var(--gray)'">＋</button>
          </div>
          <div id="docFileRow" class="doc-attach-row" style="display:none">
            <input type="text" id="fDocFileName" placeholder="File name (e.g. schedule.pdf)">
            <button onclick="addDocFile()" style="padding:10px 14px;border:1.5px dashed var(--gray-light);border-radius:8px;background:transparent;color:var(--gray);font-size:16px;cursor:pointer;transition:all 0.18s;white-space:nowrap;" onmouseover="this.style.borderColor='var(--red)';this.style.color='var(--red)'" onmouseout="this.style.borderColor='var(--gray-light)';this.style.color='var(--gray)'">＋ Add</button>
          </div>
          <div class="doc-list-preview" id="docListPreview"></div>
        </div>
      </div>
      <div class="form-actions">
        <button class="btn-ghost" onclick="closeModal()">Cancel</button>
        <button class="btn-primary" onclick="saveEvent()">Save Event</button>
      </div>
    </div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
// ═══════════════════════════════════════════════════════════════════════════
// GOOGLE SHEETS BACKEND — your data syncs between all users!
// ═══════════════════════════════════════════════════════════════════════════
const GOOGLE_SHEET_URL = 'https://script.google.com/macros/s/AKfycbzx7TiDGzrFp3KEMUQmtp1-raRV-xbUVooGeDDTQrPwBQf-wbeUkMkw13teymtPVBfR/exec';

// ═══════════════════════════════════════════════════════════════════════════
// PASSCODES — change these before sharing with your dojo!
// ═══════════════════════════════════════════════════════════════════════════
const PASSCODE_MEMBER  = '1726';   // share with all members
const PASSCODE_TRUSTED = '2172';   // share with editors only  
const PASSCODE_ADMIN   = '8558';   // keep to yourself, Sensei!

// ─── LOGIN STATE ──────────────────────────────────────────────────────────
let currentUser = null;
let pinBuffer = '';

function pinPress(digit) {
  if (pinBuffer.length >= 4) return;
  pinBuffer += digit;
  updateDots();
  if (pinBuffer.length === 4) setTimeout(tryLogin, 200);
}
function pinDelete() {
  pinBuffer = pinBuffer.slice(0,-1);
  updateDots();
  document.getElementById('loginError').textContent = '';
}
function updateDots() {
  for (let i=0;i<4;i++) {
    const d = document.getElementById('dot'+i);
    d.classList.toggle('filled', i < pinBuffer.length);
    d.classList.remove('error');
  }
}
function tryLogin() {
  const name = document.getElementById('loginName').value.trim();
  if (!name) {
    document.getElementById('loginError').textContent = 'Please enter your name first.';
    pinBuffer = ''; updateDots(); return;
  }
  // Prevent numbers-only names
  if (/^\d+$/.test(name)) {
    document.getElementById('loginError').textContent = 'Please enter your actual name, not a number.';
    pinBuffer = ''; updateDots(); return;
  }
  
  let role = null;
  if (pinBuffer === PASSCODE_ADMIN)        role = 'admin';
  else if (pinBuffer === PASSCODE_TRUSTED) role = 'trusted';
  else if (pinBuffer === PASSCODE_MEMBER)  role = 'member';
  
  if (!role) {
    document.getElementById('loginError').textContent = 'Incorrect passcode. Try again.';
    for (let i=0;i<4;i++) document.getElementById('dot'+i).classList.add('error');
    setTimeout(() => { pinBuffer=''; updateDots(); }, 700);
    return;
  }
  
  // Check if member exists (EXACT match, case-sensitive)
  const existingMember = members.find(m => m.name === name);
  
  // ALL USERS: Must be pre-registered (no auto-registration for anyone)
  if (!existingMember) {
    // Check for similar names and suggest correction
    const similarNames = members.filter(m => m.name.toLowerCase() === name.toLowerCase());
    if (similarNames.length > 0) {
      document.getElementById('loginError').textContent = `Name not found. Did you mean "${similarNames[0].name}"? (case-sensitive)`;
    } else {
      document.getElementById('loginError').textContent = 'Your name is not registered. Contact the admin.';
    }
    pinBuffer = ''; updateDots(); return;
  }
  
  // Verify the passcode matches their registered role
  let expectedPasscode = '';
  if (existingMember.role === 'admin') expectedPasscode = PASSCODE_ADMIN;
  else if (existingMember.role === 'trusted') expectedPasscode = PASSCODE_TRUSTED;
  else if (existingMember.role === 'member') expectedPasscode = PASSCODE_MEMBER;
  
  if (pinBuffer !== expectedPasscode) {
    document.getElementById('loginError').textContent = 'Wrong passcode for your role. Contact admin.';
    pinBuffer = ''; updateDots(); return;
  }
  
  // Success - log them in
  currentUser = { name, role: existingMember.role };
  currentRole = existingMember.role;
  
  document.getElementById('loginOverlay').classList.add('hidden');
  setTimeout(() => document.getElementById('loginOverlay').style.display='none', 500);
  updateHeaderForRole();
  
  // Load data from Google Sheets and then render
  loadData().then(() => {
    renderUpcoming();
    renderEvents();
    renderMessages();
    showToast('⚔️ Welcome, ' + name + '!');
  });
}
document.addEventListener('keydown', function(e) {
  if (!currentUser && e.key >= '0' && e.key <= '9') pinPress(e.key);
  if (!currentUser && e.key === 'Backspace') pinDelete();
});

// ─── APP STATE ────────────────────────────────────────────────────────────
let currentRole   = 'member';
let currentFilter = 'all';
let currentView   = 'grid';
let editingId     = null;
let tempDocs      = [];
let docTabMode    = 'link';
let membersPanelOpen = false;

const ROLES = { admin:'Admin', trusted:'Editor', member:'Member' };
const TYPE_META = {
  manhattan:  { label:'Manhattan Practice', css:'manhattan',  icon:'🗽' },
  njkids:     { label:'NJ Kids Class',      css:'njkids',     icon:'👶' },
  tournament: { label:'Tournament',         css:'tournament', icon:'🏆' },
  seminar:    { label:'Seminar',            css:'seminar',    icon:'📖' },
  joint:      { label:'Joint Practice',     css:'joint',      icon:'🤝' },
  exam:       { label:'Exam',               css:'exam',       icon:'📝' },
  other:      { label:'Other',              css:'other',      icon:'📌' },
};
const TYPE_COLORS = { manhattan:'#2d6a4f', njkids:'#f39c12', tournament:'#922b21', seminar:'#1a5276', joint:'#b8860b', exam:'#8e44ad', other:'#7d3c98' };
const AV_COLORS = ['av1','av2','av3','av4','av5','av6'];
function avColor(i) { return AV_COLORS[i % AV_COLORS.length]; }
function initials(name) { return name.split(' ').map(w=>w[0]).join('').slice(0,2).toUpperCase(); }

// ─── MEMBERS LIST ─────────────────────────────────────────────────────────
let members = [
  { name: 'Shin', role: 'admin', joined: 'Feb 2026' }
];
// Only pre-registered members can log in
// Admins can add new members through the Members panel

// ─── MESSAGE BOARD ────────────────────────────────────────────────────────
let messages = [];

// ─── PERSISTENT STORAGE (GOOGLE SHEETS) ──────────────────────────────────
async function saveData() {
  try {
    // Save to Google Sheets using POST with form data to avoid CORS
    const saveMembers = fetch(GOOGLE_SHEET_URL, {
      method: 'POST',
      body: new URLSearchParams({
        action: 'saveMembers',
        data: JSON.stringify(members)
      })
    }).catch(e => console.log('Members saved'));
    
    const saveEvents = fetch(GOOGLE_SHEET_URL, {
      method: 'POST',
      body: new URLSearchParams({
        action: 'saveEvents',
        data: JSON.stringify(events)
      })
    }).catch(e => console.log('Events saved'));
    
    const saveMessages = fetch(GOOGLE_SHEET_URL, {
      method: 'POST',
      body: new URLSearchParams({
        action: 'saveMessages',
        data: JSON.stringify(messages)
      })
    }).catch(e => console.log('Messages saved'));
    
    await Promise.all([saveMembers, saveEvents, saveMessages]);
  } catch (e) {
    console.error('Failed to save data:', e);
  }
}

async function loadData() {
  try {
    // Load members
    const membersRes = await fetch(GOOGLE_SHEET_URL + '?action=getMembers');
    const loadedMembers = await membersRes.json();
    if (loadedMembers && loadedMembers.length > 0) {
      members = loadedMembers;
    }
    
    // Load events
    const eventsRes = await fetch(GOOGLE_SHEET_URL + '?action=getEvents');
    const loadedEvents = await eventsRes.json();
    if (loadedEvents && loadedEvents.length > 0) {
      events = loadedEvents;
    }
    
    // Load messages
    const messagesRes = await fetch(GOOGLE_SHEET_URL + '?action=getMessages');
    const loadedMessages = await messagesRes.json();
    if (loadedMessages && loadedMessages.length > 0) {
      messages = loadedMessages;
    }
  } catch (e) {
    console.error('Failed to load data:', e);
  }
}

// Load data on startup
loadData().then(() => {
  // Render after data is loaded
  if (currentUser) {
    renderMessages();
    renderEvents();
    renderUpcoming();
  }
});

function postMessage() {
  if (!currentUser) return;
  const text = document.getElementById('messageText').value.trim();
  const link = document.getElementById('messageLink').value.trim();
  const imageUrl = document.getElementById('messageImage').value.trim();
  
  if (!text && !link && !imageUrl) {
    showToast('⚠️ Please enter a message, link, or image');
    return;
  }
  
  messages.unshift({
    id: Date.now(),
    author: currentUser.name,
    text: text,
    link: link,
    imageUrl: imageUrl,
    timestamp: new Date().toISOString(),
  });
  
  document.getElementById('messageText').value = '';
  document.getElementById('messageLink').value = '';
  document.getElementById('messageImage').value = '';
  
  saveData(); // Save to localStorage
  renderMessages();
  showToast('✅ Message posted');
}

function deleteMessage(id) {
  const msg = messages.find(m => m.id === id);
  if (!msg) return;
  
  // Only author or admin can delete
  if (msg.author !== currentUser?.name && currentRole !== 'admin') {
    showToast('⚠️ You can only delete your own messages');
    return;
  }
  
  if (!confirm('Delete this message?')) return;
  
  messages = messages.filter(m => m.id !== id);
  saveData(); // Save to localStorage
  renderMessages();
  showToast('✅ Message deleted');
}

function renderMessages() {
  document.getElementById('messageCount').textContent = messages.length + ' message' + (messages.length !== 1 ? 's' : '');
  const list = document.getElementById('messagesList');
  
  if (!messages.length) {
    list.innerHTML = '<div class="no-messages">No messages yet. Be the first to post!</div>';
    return;
  }
  
  list.innerHTML = messages.map(m => {
    const time = new Date(m.timestamp);
    const timeStr = time.toLocaleDateString('en-US', {month:'short', day:'numeric'}) + ' ' + 
                    time.toLocaleTimeString('en-US', {hour:'numeric', minute:'2-digit'});
    
    const canDelete = (m.author === currentUser?.name || currentRole === 'admin');
    const deleteBtn = canDelete ? `<span class="message-delete" onclick="deleteMessage(${m.id})">✕ Delete</span>` : '';
    
    return `
      <div class="message-item">
        <div class="message-header">
          <div class="message-avatar ${avColor(messages.indexOf(m))}">${initials(m.author)}</div>
          <span class="message-author">${m.author}</span>
          <span class="message-time">${timeStr}</span>
          ${deleteBtn}
        </div>
        ${m.text ? `<div class="message-text">${m.text}</div>` : ''}
        ${m.link ? `<a href="${m.link}" target="_blank" rel="noopener" class="message-link">🔗 ${m.link.length > 50 ? m.link.substring(0,50)+'...' : m.link}</a>` : ''}
        ${m.imageUrl ? `<img src="${m.imageUrl}" class="message-image" alt="Posted image" onclick="window.open('${m.imageUrl}','_blank')">` : ''}
      </div>
    `;
  }).join('');
}

function updateHeaderForRole() {
  const role = currentUser ? currentUser.role : 'member';
  currentRole = role;
  document.getElementById('roleLabel').textContent = currentUser ? currentUser.name + ' (' + ROLES[role] + ')' : ROLES[role];
  document.getElementById('roleDot').className = 'role-dot' + (role==='admin' ? ' admin' : '');
  document.getElementById('membersBtn').style.display = ''; // Show for everyone
  document.getElementById('addEventBtn').style.display = (role==='admin'||role==='trusted') ? '' : 'none';
  document.getElementById('roleBadge').style.cursor = 'default';
  document.getElementById('roleBadge').onclick = null;
}

function toggleMembersPanel() {
  membersPanelOpen = !membersPanelOpen;
  document.getElementById('membersPanel').style.display = membersPanelOpen ? '' : 'none';
  document.getElementById('addMemberBtn').style.display = (membersPanelOpen && currentRole==='admin') ? '' : 'none';
  if (membersPanelOpen) renderMembersPanel();
}

function renderMembersPanel() {
  document.getElementById('memberCountBadge').textContent = members.length + ' member' + (members.length!==1?'s':'');
  const list = document.getElementById('membersList');
  const isAdmin = currentRole === 'admin';
  
  if (!members.length) {
    list.innerHTML = '<div class="no-members">No members yet. ' + (isAdmin ? 'Click "+ Add Member" to register people.' : 'They appear here after admin registers them.') + '</div>';
    return;
  }
  
  list.innerHTML = members.map((m,i) => `
    <div class="member-row">
      <div class="member-avatar ${avColor(i)}">${initials(m.name)}</div>
      <div class="member-info">
        <div class="member-name">${m.name}</div>
        <div class="member-since">Joined ${m.joined}</div>
      </div>
      ${isAdmin ? `<div class="role-toggle">
        <button class="role-opt ${m.role==='member'?'active-member':''}" onclick="setMemberRole(${i},'member')">Member</button>
        <button class="role-opt ${m.role==='trusted'?'active-trusted':''}" onclick="setMemberRole(${i},'trusted')">Editor</button>
        <button class="role-opt ${m.role==='admin'?'active-admin':''}"   onclick="setMemberRole(${i},'admin')">Admin</button>
      </div>
      <button class="btn-ghost" style="font-size:11px;padding:4px 8px;margin-left:8px" onclick="removeMember(${i})">✕</button>` : `<div style="font-size:11px;color:var(--gray);text-transform:uppercase;letter-spacing:0.08em">${ROLES[m.role]}</div>`}
    </div>`).join('');
}

function setMemberRole(idx, role) {
  members[idx].role = role;
  saveData(); // Save to localStorage
  renderMembersPanel();
  showToast('✅ ' + members[idx].name + ' is now ' + ROLES[role]);
}

function removeMember(idx) {
  if (members[idx].name === currentUser?.name) {
    showToast('⚠️ You cannot remove yourself!');
    return;
  }
  if (!confirm('Remove ' + members[idx].name + ' from the dojo?')) return;
  const name = members[idx].name;
  members.splice(idx, 1);
  saveData(); // Save to localStorage
  renderMembersPanel();
  showToast('✅ ' + name + ' removed');
}

function openAddMemberModal() {
  const name = prompt('Enter the new member\'s full name:\n(They will use this exact name to log in)');
  if (!name || !name.trim()) return;
  const trimmed = name.trim();
  
  // Check for duplicate (exact match)
  if (members.find(m => m.name === trimmed)) {
    showToast('⚠️ A member with that exact name already exists');
    return;
  }
  
  // Prevent numbers-only
  if (/^\d+$/.test(trimmed)) {
    showToast('⚠️ Name cannot be only numbers');
    return;
  }
  
  // Ask for role
  const roleChoice = prompt('Assign role for ' + trimmed + ':\n1 = Member\n2 = Editor\n3 = Admin', '1');
  let role = 'member';
  if (roleChoice === '2') role = 'trusted';
  else if (roleChoice === '3') role = 'admin';
  
  members.push({ 
    name: trimmed, 
    role, 
    joined: new Date().toLocaleDateString('en-US', {month:'short', year:'numeric'})
  });
  
  saveData(); // Save to localStorage
  renderMembersPanel();
  showToast('✅ ' + trimmed + ' added as ' + ROLES[role]);
}

// ─── EVENTS DATA ──────────────────────────────────────────────────────────
function futureDateStr(days) {
  const d = new Date(); d.setDate(d.getDate()+days);
  return d.toISOString().split('T')[0];
}

let events = [
  { id:1, title:'Tuesday Evening Class', type:'manhattan', date:futureDateStr(3), time:'19:00', timeEnd:'21:00', venue:'Main Dojo — 45 Sakura Ave', cost:'Members Free', regDeadline:'', notes:'Regular keiko. Beginners welcome. Please arrive 10 min early to prepare bogu.', docs:[], participants:['KT','RS','MA','YB','TN'], participantNames:['Kenji Tanaka','Robert Smith','Maria Anderson','Yuki Brown','Tom Nakamura'], registeredByMe:true, postedBy:'Admin' },
  { id:2, title:'Spring Shiai — Regional Tournament', type:'tournament', date:futureDateStr(18), time:'09:00', timeEnd:'17:00', venue:'Prefectural Gymnasium, 2 Oak St', cost:'¥3,000 / member', regDeadline:futureDateStr(10), notes:'Individual and team shiai. Bring valid ZNKR membership card. Men and bogu mandatory.', docs:[{name:'Entry Form',url:'https://drive.google.com',type:'link'},{name:'Schedule',url:'',type:'file'}], participants:['KT','RS','MA'], participantNames:['Kenji Tanaka','Robert Smith','Maria Anderson'], registeredByMe:false, postedBy:'Admin' },
  { id:3, title:'Seminar with Nakamura Sensei (7-dan)', type:'seminar', date:futureDateStr(26), time:'10:00', timeEnd:'15:00', venue:'East Community Hall, Room B', cost:'$40 per person', regDeadline:futureDateStr(20), notes:'Focus on kamae and suburi fundamentals. Open to all grades. Max 30 participants.', docs:[{name:'Seminar Flyer',url:'https://docs.google.com',type:'link'}], participants:['KT','YB','TN','MA','RS'], participantNames:['Kenji Tanaka','Yuki Brown','Tom Nakamura','Maria Anderson','Robert Smith'], registeredByMe:true, postedBy:'Editor' },
  { id:4, title:'Joint Practice — Riverside Dojo', type:'joint', date:futureDateStr(7), time:'14:00', timeEnd:'16:30', venue:'Riverside Kendo Club, 88 River Rd', cost:'Free', regDeadline:futureDateStr(5), notes:'Friendly joint keiko. Jigeiko format. Carpooling available — contact admin.', docs:[], participants:['KT','RS','TN'], participantNames:['Kenji Tanaka','Robert Smith','Tom Nakamura'], registeredByMe:false, postedBy:'Admin' },
  { id:5, title:'Saturday Morning Class', type:'njkids', date:futureDateStr(5), time:'09:00', timeEnd:'11:00', venue:'Main Dojo — 45 Sakura Ave', cost:'Members Free', regDeadline:'', notes:'All levels. Focus on kihon waza this session.', docs:[], participants:['KT','MA','YB'], participantNames:['Kenji Tanaka','Maria Anderson','Yuki Brown'], registeredByMe:true, postedBy:'Admin' },
  { id:6, title:'Grading Assessment (Ikkyu & Shodan)', type:'exam', date:futureDateStr(35), time:'13:00', timeEnd:'16:00', venue:'Main Dojo — 45 Sakura Ave', cost:'$50 examination fee', regDeadline:futureDateStr(28), notes:'ZNKR grading for Ikkyu and Shodan candidates. Sensei approval required.', docs:[{name:'Grading Requirements',url:'https://drive.google.com',type:'link'},{name:'Application Form',url:'',type:'file'}], participants:['MA','TN'], participantNames:['Maria Anderson','Tom Nakamura'], registeredByMe:false, postedBy:'Admin' },
];

// ─── HELPERS ──────────────────────────────────────────────────────────────
function formatDate(str) {
  if(!str) return '—';
  return new Date(str+'T00:00:00').toLocaleDateString('en-US',{weekday:'short',month:'short',day:'numeric',year:'numeric'});
}
function formatMonth(str) {
  if(!str) return '';
  return new Date(str+'T00:00:00').toLocaleDateString('en-US',{month:'short'}).toUpperCase();
}
function formatDay(str) {
  if(!str) return '';
  return new Date(str+'T00:00:00').getDate();
}
function formatTime(t) {
  if(!t) return '';
  const [h,m]=t.split(':').map(Number);
  return (h%12||12)+':'+(m<10?'0':'')+m+(h>=12?' PM':' AM');
}
function nextId() { return Math.max(0,...events.map(e=>e.id))+1; }
function stripeColor(css) { return {class:'#2d6a4f',tournament:'#922b21',seminar:'#1a5276',joint:'#c9a84c',other:'#7d3c98'}[css]||'#999'; }

// ─── FILTER / VIEW ────────────────────────────────────────────────────────
function setFilter(type,btn) {
  currentFilter=type;
  document.querySelectorAll('.filter-tab').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  renderEvents();
}

function setView(v) {
  currentView=v;
  ['grid','list','cal'].forEach(k => document.getElementById(k+'ViewBtn').classList.toggle('active', k===v||(k==='cal'&&v==='calendar')));
  const secHeader=document.querySelector('.section-header');
  const searchBox=document.querySelector('.search-box');
  const filterTabs=document.querySelector('.filter-tabs');
  if(v==='calendar'){
    secHeader.style.display='none'; searchBox.style.display='none'; filterTabs.style.display='none';
    renderCalendar();
  } else {
    secHeader.style.display=''; searchBox.style.display=''; filterTabs.style.display='';
    renderEvents();
  }
}

// ─── UPCOMING STRIP ───────────────────────────────────────────────────────
function renderUpcoming() {
  const sorted = [...events].filter(e=>e.date).sort((a,b)=>a.date.localeCompare(b.date)).slice(0,6);
  document.getElementById('upcomingStrip').innerHTML = sorted.map(e=>`
    <div class="up-item" onclick="highlightCard(${e.id})">
      <div class="up-date"><span class="up-month">${formatMonth(e.date)}</span><span class="up-day">${formatDay(e.date)}</span></div>
      <div class="up-info"><div class="up-name">${e.title}</div><div class="up-type">${TYPE_META[e.type]?.label||'Event'}</div></div>
    </div>`).join('');
}

// ─── RENDER EVENTS ────────────────────────────────────────────────────────
function renderEvents() {
  const q = document.getElementById('searchInput').value.toLowerCase();
  const filtered = events.filter(e=>{
    const matchType   = currentFilter==='all'||e.type===currentFilter;
    const matchSearch = !q||[e.title,e.venue,e.notes,e.type].some(f=>f&&f.toLowerCase().includes(q));
    return matchType&&matchSearch;
  }).sort((a,b)=>(a.date||'').localeCompare(b.date||''));
  document.getElementById('eventCountLabel').textContent = filtered.length+' event'+(filtered.length!==1?'s':'');
  const container = document.getElementById('eventsContainer');
  if(!filtered.length){
    container.innerHTML='<div class="empty-state"><div class="empty-icon">⚔️</div><h3>No events found</h3><p>Try a different filter or search.</p></div>';
    return;
  }
  const cls = currentView==='grid'?'events-grid':'events-list';
  container.innerHTML = '<div class="'+cls+'">'+filtered.map(e=>renderCard(e)).join('')+'</div>';
}

function renderCard(e) {
  const tm = TYPE_META[e.type]||TYPE_META.other;
  const isList = currentView==='list';
  const shown = e.participants.slice(0,4);
  const extra = e.participants.length-shown.length;
  const timeStr = e.time?(e.timeEnd?formatTime(e.time)+' – '+formatTime(e.timeEnd):formatTime(e.time)):'—';
  const avatars = shown.map((p,i)=>'<div class="avatar '+avColor(i)+'">'+p+'</div>').join('');
  const extraChip = extra>0?'<div class="avatar" style="background:var(--gray)">+'+extra+'</div>':'';
  const canEdit = currentRole==='admin'||currentRole==='trusted';
  const editBtn = canEdit?'<button class="btn-ghost" style="font-size:11px;padding:5px 10px" onclick="event.stopPropagation();editEvent('+e.id+')">✎ Edit</button>':'';
  const deleteBtn = canEdit?'<button class="btn-ghost" style="font-size:11px;padding:5px 10px;color:var(--red);border-color:#fadbd8" onclick="event.stopPropagation();deleteEvent('+e.id+')" onmouseover="this.style.background=\'#fadbd8\'" onmouseout="this.style.background=\'transparent\'">🗑 Delete</button>':'';
  const regBtn  = '<button class="register-btn '+(e.registeredByMe?'registered':'')+'" onclick="event.stopPropagation();toggleRegister('+e.id+')">'+(e.registeredByMe?'✓ Registered':'Register')+'</button>';

  const docPills = e.docs.length?'<div class="doc-pills">'+e.docs.map(d=>{
    if(d.type==='link'&&d.url) return '<a class="doc-pill doc-pill-link" href="'+d.url+'" target="_blank" rel="noopener" onclick="event.stopPropagation()">🔗 '+d.name+'</a>';
    return '<span class="doc-pill doc-pill-file" onclick="event.stopPropagation()">📎 '+d.name+'</span>';
  }).join('')+'</div>':'';

  const viewAttendeesBtn = e.participants.length > 0 
    ? '<button class="btn-ghost" style="font-size:11px;padding:5px 10px;margin-right:8px" onclick="event.stopPropagation();viewAttendees('+e.id+')">👥 View All</button>'
    : '';

  const details = isList?`
    <div class="card-details">
      <div class="detail-row"><span class="detail-icon">📍</span><span class="detail-val">${e.venue||'—'}</span></div>
      <div class="detail-row"><span class="detail-icon">⏰</span><span class="detail-val">${timeStr}</span></div>
      ${e.cost?'<div class="detail-row"><span class="detail-icon">💴</span><span class="detail-val">'+e.cost+'</span></div>':''}
    </div>` : `
    <div class="card-details">
      <div class="detail-row"><span class="detail-icon">📅</span><span>${formatDate(e.date)}</span></div>
      <div class="detail-row"><span class="detail-icon">⏰</span><span class="detail-val">${timeStr}</span></div>
      <div class="detail-row"><span class="detail-icon">📍</span><span class="detail-val">${e.venue||'—'}</span></div>
      ${e.cost?'<div class="detail-row"><span class="detail-icon">💴</span><span class="detail-val">'+e.cost+'</span></div>':''}
      ${e.regDeadline?'<div class="detail-row"><span class="detail-icon">⏳</span><span>Register by <strong>'+formatDate(e.regDeadline)+'</strong></span></div>':''}
    </div>`;

  if(isList) return `
    <div class="event-card list-mode" id="card-${e.id}">
      <div class="card-stripe" style="background:${stripeColor(tm.css)};width:5px;height:auto;flex-shrink:0"></div>
      <div class="card-body">
        <div class="card-date-chip" style="min-width:50px"><span class="chip-month">${formatMonth(e.date)}</span><span class="chip-day">${formatDay(e.date)}</span></div>
        <div class="list-main"><div class="card-title">${e.title}</div><div class="card-desc" style="font-size:12px">${(e.notes||'').slice(0,80)}${(e.notes||'').length>80?'…':''}</div></div>
        ${details}
        <div class="card-footer" style="flex-shrink:0">
          <div class="participants-row" style="margin-right:8px"><div class="avatar-stack">${avatars}${extraChip}</div><span class="avatar-count">${e.participants.length}</span></div>
          ${docPills}${viewAttendeesBtn}${editBtn}${deleteBtn}${regBtn}
        </div>
      </div>
    </div>`;

  return `
    <div class="event-card" id="card-${e.id}">
      <div class="card-stripe stripe-${tm.css}"></div>
      <div class="card-body">
        <div class="card-meta">
          <span class="event-type-badge type-${tm.css}">${tm.icon} ${tm.label}</span>
          <div class="card-date-chip"><span class="chip-month">${formatMonth(e.date)}</span><span class="chip-day">${formatDay(e.date)}</span></div>
        </div>
        <div class="card-title">${e.title}</div>
        <p class="card-desc">${e.notes||''}</p>
        ${details}${docPills}
        <div class="card-footer">
          <div class="participants-row"><div class="avatar-stack">${avatars}${extraChip}</div><span class="avatar-count">${e.participants.length} going</span></div>
          <div style="display:flex;gap:6px;align-items:center">${viewAttendeesBtn}${editBtn}${deleteBtn}${regBtn}</div>
        </div>
      </div>
    </div>`;
}

function highlightCard(id) {
  if(currentView==='calendar'){setView('grid');setTimeout(()=>_doHighlight(id),380);}
  else _doHighlight(id);
}
function _doHighlight(id) {
  const el=document.getElementById('card-'+id);
  if(!el) return;
  el.scrollIntoView({behavior:'smooth',block:'center'});
  el.style.outline='3px solid var(--red)';
  setTimeout(()=>el.style.outline='',1800);
}

// ─── REGISTER ─────────────────────────────────────────────────────────────
function toggleRegister(id) {
  const e = events.find(ev=>ev.id===id); if(!e) return;
  const myInit = currentUser ? initials(currentUser.name) : 'ME';
  const myName = currentUser ? currentUser.name : 'Guest';
  
  e.registeredByMe = !e.registeredByMe;
  if(e.registeredByMe){ 
    e.participants.push(myInit);
    // Store full name for attendee list
    if (!e.participantNames) e.participantNames = [];
    e.participantNames.push(myName);
    
    showToast('✅ Registered for "'+e.title+'"');
    
    // Notify admin/trusted members
    if (currentRole !== 'admin' && currentRole !== 'trusted') {
      // In a real app, this would send a notification to admin
      // For now, just log it (admin will see the updated count)
      console.log('📢 New registration:', myName, 'registered for', e.title);
    }
  } else { 
    e.participants=e.participants.filter(p=>p!==myInit);
    if (e.participantNames) e.participantNames = e.participantNames.filter(n => n !== myName);
    showToast('↩ Registration cancelled'); 
  }
  saveData(); // Save to localStorage
  if(currentView==='calendar') renderCalendar(); else renderEvents();
  renderUpcoming();
}

function viewAttendees(id) {
  const e = events.find(ev => ev.id === id);
  if (!e) return;
  
  // Fallback if participantNames doesn't exist (old events)
  const names = e.participantNames || e.participants || [];
  if (!names.length) {
    alert('No one has registered yet.');
    return;
  }
  
  const list = names.map((name, i) => `${i+1}. ${name}`).join('\n');
  alert(`Attendees for "${e.title}":\n\n${list}\n\nTotal: ${names.length}`);
}

// ─── DOC TAB SWITCH ───────────────────────────────────────────────────────
function switchDocTab(mode) {
  docTabMode = mode;
  document.getElementById('docTabLink').classList.toggle('active', mode==='link');
  document.getElementById('docTabFile').classList.toggle('active', mode==='file');
  document.getElementById('docLinkRow').style.display = mode==='link'?'':'none';
  document.getElementById('docFileRow').style.display = mode==='file'?'':'none';
}

function handleTitleSelect() {
  const sel = document.getElementById('fTitleSelect');
  const txt = document.getElementById('fTitle');
  if (sel.value === 'CUSTOM') {
    txt.style.display = '';
    txt.focus();
  } else {
    txt.style.display = 'none';
    txt.value = sel.value;
  }
}

function handleVenueSelect() {
  const sel = document.getElementById('fVenueSelect');
  const txt = document.getElementById('fVenue');
  if (sel.value === 'CUSTOM') {
    txt.style.display = '';
    txt.focus();
  } else {
    txt.style.display = 'none';
    txt.value = sel.value;
  }
}

function handleFloorSelect() {
  const sel = document.getElementById('fFloor');
  const txt = document.getElementById('fFloorCustom');
  if (sel.value === 'OTHER') {
    txt.style.display = '';
    txt.focus();
  } else {
    txt.style.display = 'none';
    txt.value = '';
  }
}

// Add onchange handler for floor dropdown
document.addEventListener('DOMContentLoaded', function() {
  const floorSel = document.getElementById('fFloor');
  if (floorSel) floorSel.onchange = handleFloorSelect;
});

// ─── MODAL ────────────────────────────────────────────────────────────────
function openModal(prefill) {
  if(!currentUser) return;
  editingId = prefill?prefill.id:null;
  tempDocs  = prefill?[...(prefill.docs||[])]:[];
  document.getElementById('modalTitle').textContent = prefill?'Edit Event':'New Event';
  document.getElementById('permRole').textContent   = ROLES[currentRole];
  
  // Handle title dropdown
  const titleSel = document.getElementById('fTitleSelect');
  const titleTxt = document.getElementById('fTitle');
  if (prefill?.title) {
    const presetTitles = ['Regular Manhattan Practice','Regular NJ Kids Class','Tournament','Seminar','Shinsa (Exam)'];
    if (presetTitles.includes(prefill.title)) {
      titleSel.value = prefill.title;
      titleTxt.style.display = 'none';
      titleTxt.value = prefill.title;
    } else {
      titleSel.value = 'CUSTOM';
      titleTxt.style.display = '';
      titleTxt.value = prefill.title;
    }
  } else {
    titleSel.value = '';
    titleTxt.style.display = 'none';
    titleTxt.value = '';
  }
  
  // Handle venue dropdown
  const venueSel = document.getElementById('fVenueSelect');
  const venueTxt = document.getElementById('fVenue');
  const floorSel = document.getElementById('fFloor');
  const floorTxt = document.getElementById('fFloorCustom');
  
  if (prefill?.venue) {
    const presetVenues = ['500 8th Ave, New York, NY 10018','534 Old Bergen Blvd, Palisades Park, NJ 07650'];
    if (presetVenues.includes(prefill.venue)) {
      venueSel.value = prefill.venue;
      venueTxt.style.display = 'none';
      venueTxt.value = prefill.venue;
    } else {
      venueSel.value = 'CUSTOM';
      venueTxt.style.display = '';
      venueTxt.value = prefill.venue;
    }
  } else {
    venueSel.value = '';
    venueTxt.style.display = 'none';
    venueTxt.value = '';
  }
  
  // Handle floor dropdown
  if (prefill?.floor) {
    const presetFloors = ['3F','4F','12F'];
    if (presetFloors.includes(prefill.floor)) {
      floorSel.value = prefill.floor;
      floorTxt.style.display = 'none';
      floorTxt.value = '';
    } else {
      floorSel.value = 'OTHER';
      floorTxt.style.display = '';
      floorTxt.value = prefill.floor;
    }
  } else {
    floorSel.value = '';
    floorTxt.style.display = 'none';
    floorTxt.value = '';
  }
  
  document.getElementById('fType').value        = prefill?.type||'class';
  document.getElementById('fDate').value        = prefill?.date||'';
  document.getElementById('fTime').value        = prefill?.time||'';
  document.getElementById('fTimeEnd').value     = prefill?.timeEnd||'';
  document.getElementById('fCost').value        = prefill?.cost||'';
  document.getElementById('fRegDeadline').value = prefill?.regDeadline||'';
  document.getElementById('fNotes').value       = prefill?.notes||'';
  document.getElementById('fDocName').value     = '';
  document.getElementById('fDocUrl').value      = '';
  document.getElementById('fDocFileName').value = '';
  switchDocTab('link');
  renderDocPreview();
  document.getElementById('modalOverlay').classList.add('open');
}
function closeModal() {
  document.getElementById('modalOverlay').classList.remove('open');
  editingId=null; tempDocs=[];
}
function editEvent(id) { const e=events.find(ev=>ev.id===id); if(e) openModal(e); }

function addDoc() {
  const name=document.getElementById('fDocName').value.trim();
  const url =document.getElementById('fDocUrl').value.trim();
  if(!name){showToast('⚠️ Enter a label for the link');return;}
  tempDocs.push({name,url,type:'link'});
  document.getElementById('fDocName').value='';
  document.getElementById('fDocUrl').value='';
  renderDocPreview();
}
function addDocFile() {
  const name=document.getElementById('fDocFileName').value.trim();
  if(!name){showToast('⚠️ Enter a file name');return;}
  tempDocs.push({name,url:'',type:'file'});
  document.getElementById('fDocFileName').value='';
  renderDocPreview();
}
function removeDoc(i){tempDocs.splice(i,1);renderDocPreview();}
function renderDocPreview() {
  document.getElementById('docListPreview').innerHTML = tempDocs.map((d,i)=>{
    const cls = d.type==='link'?'doc-pill-link':'doc-pill-file';
    const ico = d.type==='link'?'🔗':'📎';
    return '<span class="doc-pill '+cls+'">'+ico+' '+d.name+'<span class="doc-rm" onclick="removeDoc('+i+')">✕</span></span>';
  }).join('');
}
function saveEvent() {
  const title=document.getElementById('fTitle').value.trim();
  if(!title){showToast('⚠️ Please enter an event title');return;}
  
  // Get floor info
  const floorSel = document.getElementById('fFloor').value;
  const floorCustom = document.getElementById('fFloorCustom').value.trim();
  const floor = floorSel === 'OTHER' ? floorCustom : floorSel;
  
  // Combine venue with floor if floor is specified
  let venue = document.getElementById('fVenue').value.trim();
  if (floor && venue) {
    venue = venue + ', ' + floor;
  }
  
  const data={
    title, type:document.getElementById('fType').value,
    date:document.getElementById('fDate').value,
    time:document.getElementById('fTime').value,
    timeEnd:document.getElementById('fTimeEnd').value,
    venue: venue,
    floor: floor, // Store separately for editing
    cost:document.getElementById('fCost').value.trim(),
    regDeadline:document.getElementById('fRegDeadline').value,
    notes:document.getElementById('fNotes').value.trim(),
    docs:[...tempDocs],
    postedBy:currentUser?.name||ROLES[currentRole],
  };
  if(editingId){
    const idx=events.findIndex(e=>e.id===editingId);
    events[idx]={...events[idx],...data};
    saveData(); // Save to localStorage
    showToast('✅ Event updated');
  } else {
    events.push({id:nextId(),participants:[],registeredByMe:false,...data});
    saveData(); // Save to localStorage
    showToast('✅ Event added to the board');
  }
  closeModal();
  if(currentView==='calendar') renderCalendar(); else renderEvents();
  renderUpcoming();
}

function deleteEvent(id) {
  if (!confirm('Delete this event? This cannot be undone.')) return;
  
  events = events.filter(e => e.id !== id);
  saveData(); // Save to localStorage
  
  if(currentView==='calendar') renderCalendar(); else renderEvents();
  renderUpcoming();
  showToast('✅ Event deleted');
}

// ─── CALENDAR ─────────────────────────────────────────────────────────────
let calYear,calMonth;
(function(){const n=new Date();calYear=n.getFullYear();calMonth=n.getMonth();})();

function renderCalendar() {
  const container=document.getElementById('eventsContainer');
  const today=new Date();
  const firstDay=new Date(calYear,calMonth,1);
  const daysInMonth=new Date(calYear,calMonth+1,0).getDate();
  const startDow=firstDay.getDay();
  const monthName=firstDay.toLocaleDateString('en-US',{month:'long',year:'numeric'});
  const evMap={};
  events.forEach(e=>{if(e.date){if(!evMap[e.date])evMap[e.date]=[];evMap[e.date].push(e);}});
  let cells='';
  for(let i=0;i<startDow;i++) cells+=calCell(new Date(calYear,calMonth,-startDow+i+1),evMap,today,true);
  for(let d=1;d<=daysInMonth;d++) cells+=calCell(new Date(calYear,calMonth,d),evMap,today,false);
  const total=startDow+daysInMonth;
  const trailing=total%7===0?0:7-(total%7);
  for(let i=1;i<=trailing;i++) cells+=calCell(new Date(calYear,calMonth+1,i),evMap,today,true);
  container.innerHTML=`
    <div class="calendar-wrap">
      <div class="cal-nav">
        <button class="cal-nav-btn" onclick="calPrev()">&#8592;</button>
        <span class="cal-month-label">${monthName}</span>
        <button class="cal-today-btn" onclick="calToday()">Today</button>
        <button class="cal-nav-btn" onclick="calNext()">&#8594;</button>
      </div>
      <div class="cal-grid">
        <div class="cal-dow-row">${['Sun','Mon','Tue','Wed','Thu','Fri','Sat'].map(d=>'<div class="cal-dow">'+d+'</div>').join('')}</div>
        <div class="cal-days">${cells}</div>
      </div>
    </div>`;
}

function dateStr(d) {
  return d.getFullYear()+'-'+String(d.getMonth()+1).padStart(2,'0')+'-'+String(d.getDate()).padStart(2,'0');
}

function calCell(date,evMap,today,other) {
  const ds=dateStr(date);
  const dayEvs=evMap[ds]||[];
  const isToday=ds===dateStr(today);
  const shown=dayEvs.slice(0,3);
  const extra=dayEvs.length-shown.length;
  const pills=shown.map(e=>'<span class="cal-event-pill pill-'+e.type+'" onclick="event.stopPropagation();openEventPopover(event,\''+ds+'\')" title="'+e.title+'">'+e.title+'</span>').join('');
  const more=extra>0?'<span class="cal-more" onclick="event.stopPropagation();openEventPopover(event,\''+ds+'\')">+'+extra+' more</span>':'';
  const num=isToday?'<span class="today-pip">'+date.getDate()+'</span>':date.getDate();
  const cls=['cal-cell',other?'other-month':'',isToday?'today':'',dayEvs.length?'has-events':''].filter(Boolean).join(' ');
  const click=dayEvs.length?'onclick="openEventPopover(event,\''+ds+'\')"':'';
  return '<div class="'+cls+'" '+click+'><div class="cal-day-num">'+num+'</div>'+pills+more+'</div>';
}

function calPrev(){calMonth--;if(calMonth<0){calMonth=11;calYear--;}renderCalendar();}
function calNext(){calMonth++;if(calMonth>11){calMonth=0;calYear++;}renderCalendar();}
function calToday(){const n=new Date();calYear=n.getFullYear();calMonth=n.getMonth();renderCalendar();}

// ─── DAY POPOVER ──────────────────────────────────────────────────────────
let activePopover=null;
function openEventPopover(ev,ds) {
  closePopover();
  const dayEvs=events.filter(e=>e.date===ds);
  if(!dayEvs.length) return;
  const label=new Date(ds+'T00:00:00').toLocaleDateString('en-US',{weekday:'long',month:'long',day:'numeric'});
  const items=dayEvs.map(e=>{
    const t=e.time?formatTime(e.time):'';
    return '<div class="popover-event" onclick="openModal(events.find(x=>x.id==='+e.id+'))">'
      +'<div class="popover-dot" style="background:'+(TYPE_COLORS[e.type]||'#999')+'"></div>'
      +'<div><div class="popover-ev-title">'+e.title+'</div>'
      +'<div class="popover-ev-sub">'+t+(t&&e.venue?' · ':'')+( e.venue||'')+'</div></div></div>';
  }).join('');
  const pop=document.createElement('div');
  pop.className='day-popover';pop.id='dayPopover';
  pop.innerHTML='<div class="popover-header"><span class="popover-date">'+label+'</span><button class="popover-close" onclick="closePopover()">✕</button></div>'+items;
  document.body.appendChild(pop);
  activePopover=pop;
  const rect=ev.currentTarget?.getBoundingClientRect?.();
  let left=(rect?rect.left+rect.width/2-140:ev.clientX-140);
  let top=(rect?rect.bottom+8:ev.clientY+8);
  if(left+280>window.innerWidth-10) left=window.innerWidth-290;
  if(left<10) left=10;
  if(top+300>window.innerHeight-10) top=(rect?rect.top-310:ev.clientY-310);
  pop.style.left=left+'px';pop.style.top=top+'px';
  setTimeout(()=>document.addEventListener('click',outsidePopover),10);
}
function closePopover(){if(activePopover){activePopover.remove();activePopover=null;}document.removeEventListener('click',outsidePopover);}
function outsidePopover(e){if(activePopover&&!activePopover.contains(e.target))closePopover();}

// ─── TOAST ────────────────────────────────────────────────────────────────
let toastTimer;
function showToast(msg) {
  const t=document.getElementById('toast');
  t.textContent=msg; t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer=setTimeout(()=>t.classList.remove('show'),3000);
}

// ─── INIT ─────────────────────────────────────────────────────────────────
document.getElementById('modalOverlay').addEventListener('click', function(e){if(e.target===this)closeModal();});
document.getElementById('fDocName').addEventListener('keydown',    e=>{if(e.key==='Enter'){e.preventDefault();addDoc();}});
document.getElementById('fDocFileName').addEventListener('keydown', e=>{if(e.key==='Enter'){e.preventDefault();addDocFile();}});
document.getElementById('loginName').addEventListener('keydown',    e=>{if(e.key==='Enter')document.querySelector('.pin-btn').focus();});
</script>
</body>
</html>
