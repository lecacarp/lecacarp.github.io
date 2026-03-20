<html lang="ro">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>IT Academy | Cursuri IT Moderne</title>
  <style>
    :root {
      --bg: #0b1020;
      --bg-soft: #121933;
      --card: rgba(18, 25, 51, 0.8);
      --line: rgba(255,255,255,0.08);
      --text: #ecf2ff;
      --muted: #b7c3e0;
      --accent: #6ea8fe;
      --accent-2: #7ef0c7;
      --accent-3: #b38cff;
      --danger: #ff7f96;
      --shadow: 0 20px 50px rgba(0, 0, 0, 0.35);
      --radius: 24px;
      --radius-sm: 16px;
      --container: 1180px;
      --transition: 0.35s ease;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Inter, Arial, sans-serif;
      background:
        radial-gradient(circle at 15% 20%, rgba(110,168,254,0.18), transparent 25%),
        radial-gradient(circle at 80% 20%, rgba(179,140,255,0.14), transparent 25%),
        radial-gradient(circle at 50% 80%, rgba(126,240,199,0.10), transparent 30%),
        linear-gradient(180deg, #08101d 0%, #0c1224 50%, #0a1020 100%);
      color: var(--text);
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(255,255,255,0.02) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.02) 1px, transparent 1px);
      background-size: 40px 40px;
      pointer-events: none;
      z-index: -2;
    }

    .blob {
      position: fixed;
      width: 340px;
      height: 340px;
      border-radius: 50%;
      filter: blur(70px);
      opacity: 0.22;
      z-index: -1;
      animation: floatBlob 11s ease-in-out infinite;
    }

    .blob.one {
      background: var(--accent);
      top: -80px;
      left: -90px;
    }

    .blob.two {
      background: var(--accent-3);
      right: -100px;
      top: 180px;
      animation-delay: 1.5s;
    }

    .blob.three {
      background: var(--accent-2);
      left: 40%;
      bottom: -120px;
      animation-delay: 3s;
    }

    @keyframes floatBlob {
      0%, 100% { transform: translate(0,0) scale(1); }
      50% { transform: translate(25px, -18px) scale(1.08); }
    }

    .container {
      width: min(var(--container), calc(100% - 32px));
      margin: 0 auto;
    }

    .topbar {
      position: sticky;
      top: 0;
      z-index: 1000;
      backdrop-filter: blur(16px);
      background: rgba(8, 14, 30, 0.65);
      border-bottom: 1px solid var(--line);
    }

    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      min-height: 78px;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 12px;
      text-decoration: none;
      color: var(--text);
      font-weight: 800;
      letter-spacing: 0.4px;
    }

    .logo-mark {
      width: 42px;
      height: 42px;
      border-radius: 14px;
      display: grid;
      place-items: center;
      background: linear-gradient(135deg, var(--accent), var(--accent-3));
      box-shadow: var(--shadow);
      font-size: 1.1rem;
    }

    .menu {
      display: flex;
      align-items: center;
      gap: 24px;
      list-style: none;
    }

    .menu a {
      text-decoration: none;
      color: var(--muted);
      font-weight: 600;
      transition: var(--transition);
      position: relative;
    }

    .menu a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: -6px;
      width: 0;
      height: 2px;
      background: linear-gradient(90deg, var(--accent), var(--accent-2));
      transition: var(--transition);
    }

    .menu a:hover,
    .menu a.active {
      color: var(--text);
    }

    .menu a:hover::after,
    .menu a.active::after {
      width: 100%;
    }

    .nav-actions {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .btn,
    .btn-outline {
      border: none;
      outline: none;
      cursor: pointer;
      font-weight: 700;
      text-decoration: none;
      transition: var(--transition);
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 14px 22px;
      border-radius: 999px;
    }

    .btn {
      color: #06111f;
      background: linear-gradient(135deg, var(--accent-2), var(--accent));
      box-shadow: 0 10px 24px rgba(110,168,254,0.22);
    }

    .btn:hover {
      transform: translateY(-3px) scale(1.01);
    }

    .btn-outline {
      color: var(--text);
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.03);
    }

    .btn-outline:hover {
      border-color: rgba(255,255,255,0.2);
      background: rgba(255,255,255,0.06);
    }

    .menu-toggle {
      display: none;
      width: 46px;
      height: 46px;
      border-radius: 14px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
      color: var(--text);
      font-size: 1.25rem;
      cursor: pointer;
    }

    section {
      padding: 92px 0;
      position: relative;
    }

    .hero {
      padding-top: 70px;
      min-height: calc(100vh - 78px);
      display: flex;
      align-items: center;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      gap: 42px;
      align-items: center;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 10px 16px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,0.1);
      background: rgba(255,255,255,0.04);
      color: var(--accent-2);
      font-size: 0.92rem;
      margin-bottom: 22px;
      animation: fadeUp 0.9s ease both;
    }

    .eyebrow span {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: var(--accent-2);
      box-shadow: 0 0 0 6px rgba(126,240,199,0.14);
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { transform: scale(1); opacity: 1; }
      50% { transform: scale(1.3); opacity: 0.65; }
    }

    .hero h1 {
      font-size: clamp(2.8rem, 5vw, 5rem);
      line-height: 1.05;
      margin-bottom: 18px;
      animation: fadeUp 1s ease both;
    }

    .hero h1 .gradient {
      background: linear-gradient(135deg, var(--accent), var(--accent-2), var(--accent-3));
      -webkit-background-clip: text;
      color: transparent;
      background-size: 220% 220%;
      animation: gradientMove 6s linear infinite;
    }

    @keyframes gradientMove {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .hero p {
      color: var(--muted);
      font-size: 1.08rem;
      line-height: 1.8;
      max-width: 640px;
      margin-bottom: 28px;
      animation: fadeUp 1.1s ease both;
    }

    .hero-buttons,
    .hero-stats {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
    }

    .hero-buttons {
      margin-bottom: 34px;
      animation: fadeUp 1.2s ease both;
    }

    .hero-stats {
      gap: 18px;
      animation: fadeUp 1.35s ease both;
    }

    .stat-pill {
      padding: 14px 18px;
      border-radius: 18px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      min-width: 150px;
    }

    .stat-pill strong {
      display: block;
      font-size: 1.2rem;
      margin-bottom: 4px;
    }

    .stat-pill span {
      color: var(--muted);
      font-size: 0.92rem;
    }

    .hero-visual {
      position: relative;
      min-height: 560px;
      animation: floatPanel 6s ease-in-out infinite;
    }

    @keyframes floatPanel {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

    .dashboard {
      position: absolute;
      inset: 0;
      border-radius: 32px;
      background: linear-gradient(180deg, rgba(19,27,54,0.96), rgba(12,18,36,0.92));
      border: 1px solid rgba(255,255,255,0.09);
      box-shadow: var(--shadow);
      overflow: hidden;
    }

    .dashboard::before {
      content: "";
      position: absolute;
      inset: -1px;
      border-radius: inherit;
      padding: 1px;
      background: linear-gradient(135deg, rgba(110,168,254,0.55), rgba(126,240,199,0.16), rgba(179,140,255,0.45));
      -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
      -webkit-mask-composite: xor;
      mask-composite: exclude;
      pointer-events: none;
    }

    .dash-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 20px 22px;
      border-bottom: 1px solid var(--line);
    }

    .dots {
      display: flex;
      gap: 8px;
    }

    .dots span {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      background: rgba(255,255,255,0.22);
    }

    .dots span:nth-child(1) { background: #ff6f7d; }
    .dots span:nth-child(2) { background: #ffd76f; }
    .dots span:nth-child(3) { background: #7ef0c7; }

    .dash-label {
      color: var(--muted);
      font-size: 0.9rem;
    }

    .dash-content {
      padding: 22px;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 18px;
      height: calc(100% - 73px);
    }

    .panel {
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(255,255,255,0.06);
      border-radius: 22px;
      padding: 20px;
      position: relative;
      overflow: hidden;
    }

    .panel h3 {
      font-size: 1rem;
      margin-bottom: 16px;
    }

    .bars {
      display: flex;
      align-items: end;
      gap: 14px;
      height: 190px;
    }

    .bar {
      flex: 1;
      border-radius: 18px 18px 8px 8px;
      background: linear-gradient(180deg, var(--accent), var(--accent-3));
      position: relative;
      animation: growBar 1.2s ease forwards;
      transform-origin: bottom;
    }

    .bar:nth-child(2) { animation-delay: 0.15s; }
    .bar:nth-child(3) { animation-delay: 0.3s; }
    .bar:nth-child(4) { animation-delay: 0.45s; }
    .bar:nth-child(5) { animation-delay: 0.6s; }

    @keyframes growBar {
      from { transform: scaleY(0.15); opacity: 0.4; }
      to { transform: scaleY(1); opacity: 1; }
    }

    .bar::after {
      content: attr(data-label);
      position: absolute;
      bottom: -28px;
      left: 50%;
      transform: translateX(-50%);
      font-size: 0.78rem;
      color: var(--muted);
    }

    .course-mini-list {
      display: grid;
      gap: 12px;
    }

    .course-mini {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 14px;
      padding: 14px 16px;
      border-radius: 18px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.05);
      transform: translateX(24px);
      opacity: 0;
      animation: slideInCard 0.8s ease forwards;
    }

    .course-mini:nth-child(2) { animation-delay: 0.15s; }
    .course-mini:nth-child(3) { animation-delay: 0.3s; }
    .course-mini:nth-child(4) { animation-delay: 0.45s; }

    @keyframes slideInCard {
      to { transform: translateX(0); opacity: 1; }
    }

    .course-mini strong {
      display: block;
      margin-bottom: 4px;
    }

    .course-mini span,
    .course-mini small {
      color: var(--muted);
    }

    .tag {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 8px 12px;
      border-radius: 999px;
      background: rgba(110,168,254,0.14);
      color: var(--accent);
      font-size: 0.8rem;
      font-weight: 700;
      white-space: nowrap;
    }

    .floating-card {
      position: absolute;
      padding: 16px 18px;
      border-radius: 20px;
      background: rgba(9, 16, 31, 0.82);
      border: 1px solid rgba(255,255,255,0.08);
      box-shadow: var(--shadow);
      backdrop-filter: blur(16px);
      animation: floatBadge 5s ease-in-out infinite;
    }

    .floating-card strong {
      display: block;
      margin-bottom: 4px;
    }

    .floating-card small {
      color: var(--muted);
    }

    .floating-card.one {
      top: -20px;
      right: -28px;
      animation-delay: 0.4s;
    }

    .floating-card.two {
      left: -30px;
      bottom: 48px;
      animation-delay: 1.2s;
    }

    @keyframes floatBadge {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-12px); }
    }

    .section-title {
      max-width: 720px;
      margin: 0 auto 52px;
      text-align: center;
    }

    .section-title .label {
      color: var(--accent-2);
      font-weight: 800;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      display: inline-block;
      margin-bottom: 14px;
      font-size: 0.84rem;
    }

    .section-title h2 {
      font-size: clamp(2rem, 4vw, 3.2rem);
      margin-bottom: 14px;
    }

    .section-title p {
      color: var(--muted);
      line-height: 1.8;
      font-size: 1.02rem;
    }

    .features-grid,
    .courses-grid,
    .testimonials-grid,
    .footer-grid {
      display: grid;
      gap: 22px;
    }

    .features-grid {
      grid-template-columns: repeat(4, 1fr);
    }

    .feature-card,
    .course-card,
    .testimonial-card,
    .pricing-card,
    .faq-item,
    .contact-card {
      background: var(--card);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      backdrop-filter: blur(12px);
    }

    .feature-card {
      padding: 28px;
      transition: var(--transition);
      position: relative;
      overflow: hidden;
    }

    .feature-card::before {
      content: "";
      position: absolute;
      inset: auto -20% -60% auto;
      width: 140px;
      height: 140px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(110,168,254,0.22), transparent 70%);
      transition: var(--transition);
    }

    .feature-card:hover,
    .course-card:hover,
    .testimonial-card:hover,
    .pricing-card:hover,
    .contact-card:hover {
      transform: translateY(-8px);
      border-color: rgba(255,255,255,0.16);
    }

    .feature-icon {
      width: 64px;
      height: 64px;
      border-radius: 20px;
      display: grid;
      place-items: center;
      margin-bottom: 18px;
      font-size: 1.4rem;
      background: linear-gradient(135deg, rgba(110,168,254,0.2), rgba(179,140,255,0.24));
      border: 1px solid rgba(255,255,255,0.08);
    }

    .feature-card h3,
    .course-card h3,
    .pricing-card h3,
    .contact-card h3 {
      margin-bottom: 12px;
      font-size: 1.2rem;
    }

    .feature-card p,
    .course-card p,
    .pricing-card p,
    .testimonial-card p,
    .contact-card p,
    .faq-answer {
      color: var(--muted);
      line-height: 1.75;
    }

    .courses-grid {
      grid-template-columns: repeat(3, 1fr);
    }

    .course-card {
      padding: 22px;
      display: flex;
      flex-direction: column;
      gap: 18px;
      position: relative;
      overflow: hidden;
    }

    .course-card::after {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(180deg, rgba(255,255,255,0.03), transparent 40%);
      pointer-events: none;
    }

    .course-thumb {
      min-height: 190px;
      border-radius: 24px;
      overflow: hidden;
      position: relative;
      border: 1px solid rgba(255,255,255,0.06);
      background: linear-gradient(135deg, #1a2550, #131c39);
    }

    .course-thumb .shape {
      position: absolute;
      border-radius: 24px;
      opacity: 0.9;
      animation: morph 7s ease-in-out infinite;
    }

    .shape.s1 {
      width: 120px;
      height: 120px;
      background: linear-gradient(135deg, var(--accent), transparent);
      top: 18px;
      left: 18px;
    }

    .shape.s2 {
      width: 160px;
      height: 160px;
      background: linear-gradient(135deg, rgba(126,240,199,0.8), transparent);
      bottom: -12px;
      right: 20px;
      animation-delay: 1s;
    }

    .shape.s3 {
      width: 86px;
      height: 86px;
      background: linear-gradient(135deg, rgba(179,140,255,0.9), transparent);
      bottom: 30px;
      left: 34px;
      animation-delay: 2s;
    }

    @keyframes morph {
      0%,100% { transform: translate(0,0) rotate(0deg) scale(1); border-radius: 24px; }
      33% { transform: translate(14px,-10px) rotate(8deg) scale(1.08); border-radius: 36px; }
      66% { transform: translate(-10px,10px) rotate(-6deg) scale(0.96); border-radius: 44px; }
    }

    .course-header,
    .course-meta,
    .mentor-row,
    .price-row,
    .contact-items {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      flex-wrap: wrap;
    }

    .course-meta {
      color: var(--muted);
      font-size: 0.95rem;
    }

    .bullet-list {
      list-style: none;
      display: grid;
      gap: 10px;
    }

    .bullet-list li {
      position: relative;
      padding-left: 24px;
      color: var(--muted);
    }

    .bullet-list li::before {
      content: "✓";
      position: absolute;
      left: 0;
      top: 0;
      color: var(--accent-2);
      font-weight: 800;
    }

    .mentor {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .mentor-avatar {
      width: 44px;
      height: 44px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--accent), var(--accent-3));
      display: grid;
      place-items: center;
      font-weight: 800;
      color: #08101d;
    }

    .price {
      font-size: 1.3rem;
      font-weight: 800;
    }

    .progress-section {
      overflow: hidden;
    }

    .timeline-wrap {
      display: grid;
      grid-template-columns: 0.95fr 1.05fr;
      gap: 28px;
      align-items: center;
    }

    .timeline-box,
    .stats-box {
      padding: 28px;
      border-radius: 28px;
      background: var(--card);
      border: 1px solid rgba(255,255,255,0.08);
      box-shadow: var(--shadow);
    }

    .timeline {
      position: relative;
      display: grid;
      gap: 22px;
      margin-top: 22px;
    }

    .timeline::before {
      content: "";
      position: absolute;
      left: 11px;
      top: 6px;
      bottom: 6px;
      width: 2px;
      background: linear-gradient(var(--accent), var(--accent-2), var(--accent-3));
    }

    .timeline-item {
      position: relative;
      padding-left: 42px;
    }

    .timeline-item::before {
      content: "";
      position: absolute;
      width: 24px;
      height: 24px;
      left: 0;
      top: 2px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--accent), var(--accent-2));
      box-shadow: 0 0 0 8px rgba(110,168,254,0.12);
    }

    .timeline-item h4 {
      margin-bottom: 8px;
      font-size: 1.05rem;
    }

    .timeline-item p {
      color: var(--muted);
      line-height: 1.75;
    }

    .stats-box {
      display: grid;
      gap: 18px;
    }

    .ring-card {
      display: grid;
      grid-template-columns: 180px 1fr;
      gap: 22px;
      align-items: center;
      padding: 22px;
      border-radius: 24px;
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(255,255,255,0.06);
    }

    .ring {
      width: 160px;
      height: 160px;
      margin: 0 auto;
      border-radius: 50%;
      background: conic-gradient(var(--accent-2) 0 78%, rgba(255,255,255,0.08) 78% 100%);
      display: grid;
      place-items: center;
      position: relative;
      animation: spinSlow 7s linear infinite;
    }

    .ring::before {
      content: "";
      position: absolute;
      width: 112px;
      height: 112px;
      border-radius: 50%;
      background: #0f1730;
      border: 1px solid rgba(255,255,255,0.06);
    }

    .ring span {
      position: relative;
      z-index: 1;
      font-size: 1.7rem;
      font-weight: 800;
    }

    @keyframes spinSlow {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    .mini-stats {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 14px;
    }

    .mini-stat {
      padding: 18px;
      border-radius: 20px;
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(255,255,255,0.06);
    }

    .mini-stat strong {
      display: block;
      font-size: 1.2rem;
      margin-bottom: 6px;
    }

    .mini-stat span {
      color: var(--muted);
      font-size: 0.94rem;
    }

    .pricing-grid,
    .faq-grid,
    .contact-grid {
      display: grid;
      gap: 22px;
    }

    .pricing-grid {
      grid-template-columns: repeat(3, 1fr);
      align-items: stretch;
    }

    .pricing-card {
      padding: 28px;
      position: relative;
      display: flex;
      flex-direction: column;
      gap: 18px;
    }

    .pricing-card.popular {
      border-color: rgba(126,240,199,0.35);
      transform: translateY(-8px);
    }

    .popular-badge {
      position: absolute;
      top: 18px;
      right: 18px;
      padding: 8px 12px;
      border-radius: 999px;
      background: rgba(126,240,199,0.14);
      color: var(--accent-2);
      font-size: 0.78rem;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: 0.06em;
    }

    .price-big {
      font-size: 2.5rem;
      font-weight: 900;
      line-height: 1;
    }

    .price-big small {
      font-size: 1rem;
      color: var(--muted);
      font-weight: 600;
    }

    .testimonials-grid {
      grid-template-columns: repeat(3, 1fr);
    }

    .testimonial-card {
      padding: 26px;
      position: relative;
      overflow: hidden;
    }

    .testimonial-card::before {
      content: "“";
      position: absolute;
      top: -18px;
      right: 18px;
      font-size: 7rem;
      color: rgba(255,255,255,0.05);
      line-height: 1;
      font-family: Georgia, serif;
    }

    .stars {
      color: #ffd76f;
      margin-bottom: 14px;
      letter-spacing: 3px;
    }

    .testimonial-user {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-top: 18px;
    }

    .testimonial-avatar {
      width: 50px;
      height: 50px;
      border-radius: 50%;
      display: grid;
      place-items: center;
      font-weight: 800;
      background: linear-gradient(135deg, var(--accent), var(--accent-2));
      color: #09111f;
    }

    .faq-grid {
      grid-template-columns: 1fr 1fr;
      align-items: start;
    }

    .faq-list {
      display: grid;
      gap: 14px;
    }

    .faq-item {
      overflow: hidden;
    }

    .faq-question {
      width: 100%;
      border: none;
      background: transparent;
      color: var(--text);
      text-align: left;
      padding: 22px;
      font-size: 1rem;
      font-weight: 700;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
      cursor: pointer;
    }

    .faq-question span:last-child {
      font-size: 1.3rem;
      color: var(--accent-2);
      transition: var(--transition);
    }

    .faq-item.active .faq-question span:last-child {
      transform: rotate(45deg);
    }

    .faq-answer {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.4s ease, padding 0.4s ease;
      padding: 0 22px;
    }

    .faq-item.active .faq-answer {
      max-height: 220px;
      padding: 0 22px 22px;
    }

    .contact-grid {
      grid-template-columns: 0.9fr 1.1fr;
      align-items: start;
    }

    .contact-card {
      padding: 28px;
      height: 100%;
    }

    .contact-items {
      flex-direction: column;
      align-items: stretch;
      margin-top: 22px;
    }

    .contact-item {
      padding: 18px;
      border-radius: 20px;
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(255,255,255,0.06);
    }

    .contact-item strong {
      display: block;
      margin-bottom: 8px;
    }

    .contact-item span {
      color: var(--muted);
    }

    .contact-form {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 16px;
    }

    .contact-form .full {
      grid-column: 1 / -1;
    }

    .field {
      display: grid;
      gap: 8px;
    }

    .field label {
      color: var(--muted);
      font-size: 0.95rem;
    }

    .field input,
    .field select,
    .field textarea {
      width: 100%;
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 18px;
      background: rgba(255,255,255,0.04);
      color: var(--text);
      padding: 15px 16px;
      outline: none;
      transition: var(--transition);
      font: inherit;
      resize: vertical;
    }

    .field input:focus,
    .field select:focus,
    .field textarea:focus {
      border-color: rgba(110,168,254,0.55);
      box-shadow: 0 0 0 4px rgba(110,168,254,0.1);
    }

    .footer {
      padding: 28px 0 40px;
      border-top: 1px solid rgba(255,255,255,0.08);
    }

    .footer-grid {
      grid-template-columns: 1.2fr 0.8fr 0.8fr 1fr;
      align-items: start;
    }

    .footer-col h4 {
      margin-bottom: 16px;
    }

    .footer-col p,
    .footer-col a,
    .footer-note {
      color: var(--muted);
      line-height: 1.8;
      text-decoration: none;
    }

    .footer-col a:hover {
      color: var(--text);
    }

    .footer-links {
      list-style: none;
      display: grid;
      gap: 8px;
    }

    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.8s ease, transform 0.8s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    .floating-shapes {
      position: absolute;
      inset: 0;
      pointer-events: none;
      overflow: hidden;
    }

    .floating-shapes i {
      position: absolute;
      display: block;
      border-radius: 50%;
      border: 1px solid rgba(255,255,255,0.08);
      animation: drift linear infinite;
    }

    .floating-shapes i:nth-child(1) {
      width: 18px; height: 18px; left: 8%; top: 10%; animation-duration: 14s;
    }
    .floating-shapes i:nth-child(2) {
      width: 28px; height: 28px; right: 12%; top: 24%; animation-duration: 18s;
    }
    .floating-shapes i:nth-child(3) {
      width: 10px; height: 10px; left: 18%; bottom: 18%; animation-duration: 11s;
    }
    .floating-shapes i:nth-child(4) {
      width: 24px; height: 24px; right: 22%; bottom: 12%; animation-duration: 16s;
    }

    @keyframes drift {
      0% { transform: translateY(0px) rotate(0deg); opacity: 0.4; }
      50% { transform: translateY(-24px) rotate(180deg); opacity: 1; }
      100% { transform: translateY(0px) rotate(360deg); opacity: 0.4; }
    }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @media (max-width: 1100px) {
      .hero-grid,
      .timeline-wrap,
      .contact-grid,
      .faq-grid,
      .footer-grid,
      .features-grid,
      .courses-grid,
      .pricing-grid,
      .testimonials-grid {
        grid-template-columns: 1fr 1fr;
      }

      .hero-visual,
      .dashboard {
        min-height: 500px;
      }
    }

    @media (max-width: 860px) {
      .menu {
        position: absolute;
        top: 78px;
        left: 16px;
        right: 16px;
        background: rgba(8, 14, 30, 0.96);
        border: 1px solid var(--line);
        border-radius: 22px;
        padding: 18px;
        flex-direction: column;
        align-items: flex-start;
        gap: 14px;
        display: none;
      }

      .menu.open {
        display: flex;
      }

      .nav-actions .btn-outline,
      .nav-actions .btn {
        display: none;
      }

      .menu-toggle {
        display: inline-grid;
        place-items: center;
      }

      .hero-grid,
      .timeline-wrap,
      .contact-grid,
      .faq-grid,
      .footer-grid,
      .features-grid,
      .courses-grid,
      .pricing-grid,
      .testimonials-grid,
      .dash-content,
      .ring-card,
      .contact-form {
        grid-template-columns: 1fr;
      }

      .hero {
        min-height: auto;
      }

      .hero-visual {
        min-height: 540px;
      }

      .floating-card.one {
        right: 10px;
        top: -16px;
      }

      .floating-card.two {
        left: 10px;
        bottom: 16px;
      }

      .contact-form .full {
        grid-column: auto;
      }
    }

    @media (max-width: 560px) {
      section {
        padding: 74px 0;
      }

      .hero {
        padding-top: 34px;
      }

      .hero h1 {
        font-size: 2.4rem;
      }

      .dashboard {
        border-radius: 24px;
      }

      .dash-content,
      .dash-top,
      .panel,
      .feature-card,
      .course-card,
      .pricing-card,
      .testimonial-card,
      .timeline-box,
      .stats-box,
      .contact-card {
        padding-left: 18px;
        padding-right: 18px;
      }

      .hero-buttons,
      .hero-stats {
        flex-direction: column;
        align-items: stretch;
      }

      .btn,
      .btn-outline {
        width: 100%;
      }
    }
  </style>
</head>
<body>
  <div class="blob one"></div>
  <div class="blob two"></div>
  <div class="blob three"></div>

  <header class="topbar">
    <div class="container nav">
      <a href="#home" class="logo">
        <div class="logo-mark">&lt;/&gt;</div>
        <span>IT Academy</span>
      </a>

      <nav>
        <ul class="menu" id="menu">
          <li><a href="#home" class="active">Acasă</a></li>
          <li><a href="#features">Avantaje</a></li>
          <li><a href="#courses">Cursuri</a></li>
          <li><a href="#roadmap">Proces</a></li>
          <li><a href="#pricing">Prețuri</a></li>
          <li><a href="#faq">FAQ</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>

      <div class="nav-actions">
        <a href="#pricing" class="btn-outline">Vezi pachetele</a>
        <a href="#contact" class="btn">Înscrie-te</a>
        <button class="menu-toggle" id="menuToggle">☰</button>
      </div>
    </div>
  </header>

  <main>
    <section class="hero" id="home">
      <div class="floating-shapes">
        <i></i><i></i><i></i><i></i>
      </div>
      <div class="container hero-grid">
        <div>
          <div class="eyebrow"><span></span>Învață IT modern, practic și clar</div>
          <h1>
            Construiește-ți viitorul în <span class="gradient">programare, design și tech</span>
          </h1>
          <p>
            O platformă modernă de cursuri IT unde găsești trasee complete de învățare, mentori activi din industrie,
            proiecte reale, lecții video bine structurate și o experiență interactivă cu animații, micro-interacțiuni și secțiuni dinamice.
          </p>
          <div class="hero-buttons">
            <a href="#courses" class="btn">Explorează cursurile</a>
            <a href="#roadmap" class="btn-outline">Cum funcționează</a>
          </div>
          <div class="hero-stats">
            <div class="stat-pill">
              <strong>25+</strong>
              <span>Cursuri actualizate</span>
            </div>
            <div class="stat-pill">
              <strong>4.9/5</strong>
              <span>Rating mediu cursanți</span>
            </div>
            <div class="stat-pill">
              <strong>1200+</strong>
              <span>Studenți instruiți</span>
            </div>
          </div>
        </div>

        <div class="hero-visual">
          <div class="dashboard">
            <div class="dash-top">
              <div class="dots"><span></span><span></span><span></span></div>
              <div class="dash-label">Panou interactiv cursuri</div>
            </div>
            <div class="dash-content">
              <div class="panel">
                <h3>Progres pe domenii</h3>
                <div class="bars">
                  <div class="bar" style="height: 58%;" data-label="HTML"></div>
                  <div class="bar" style="height: 76%;" data-label="CSS"></div>
                  <div class="bar" style="height: 90%;" data-label="JS"></div>
                  <div class="bar" style="height: 68%;" data-label="Python"></div>
                  <div class="bar" style="height: 82%;" data-label="UI"></div>
                </div>
              </div>
              <div class="panel">
                <h3>Cursuri populare</h3>
                <div class="course-mini-list">
                  <div class="course-mini">
                    <div>
                      <strong>Front-End Web</strong>
                      <span>HTML, CSS, JavaScript</span>
                    </div>
                    <small class="tag">Top</small>
                  </div>
                  <div class="course-mini">
                    <div>
                      <strong>Python Start</strong>
                      <span>Baze + proiecte practice</span>
                    </div>
                    <small class="tag">Nou</small>
                  </div>
                  <div class="course-mini">
                    <div>
                      <strong>UI/UX Design</strong>
                      <span>Figma, prototipuri, layout</span>
                    </div>
                    <small class="tag">Design</small>
                  </div>
                  <div class="course-mini">
                    <div>
                      <strong>Data Analytics</strong>
                      <span>Excel, SQL, dashboard</span>
                    </div>
                    <small class="tag">Pro</small>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <div class="floating-card one">
            <strong>Live mentoring</strong>
            <small>Întâlniri săptămânale cu feedback</small>
          </div>
          <div class="floating-card two">
            <strong>Portofoliu real</strong>
            <small>Proiecte pe care le poți arăta angajatorilor</small>
          </div>
        </div>
      </div>
    </section>

    <section id="features">
      <div class="container">
        <div class="section-title reveal">
          <span class="label">De ce noi</span>
          <h2>Experiență completă de învățare pentru cursuri IT</h2>
          <p>
            Site-ul este gândit ca o prezentare premium pentru o academie IT: design modern, secțiuni bogate, animații,
            tranziții line și conținut clar pentru conversie și informare.
          </p>
        </div>

        <div class="features-grid">
          <article class="feature-card reveal">
            <div class="feature-icon">⚡</div>
            <h3>Lecții interactive</h3>
            <p>Lecții structurate logic, exemple pas cu pas, recapitulări și exerciții practice după fiecare modul.</p>
          </article>
          <article class="feature-card reveal">
            <div class="feature-icon">🎯</div>
            <h3>Proiecte reale</h3>
            <p>Nu înveți doar teorie. Construiești site-uri, aplicații, prototipuri și dashboard-uri pe care le poți include în portofoliu.</p>
          </article>
          <article class="feature-card reveal">
            <div class="feature-icon">🧠</div>
            <h3>Mentorat dedicat</h3>
            <p>Primești feedback personalizat, clarificări rapide și recomandări concrete pentru a evolua constant.</p>
          </article>
          <article class="feature-card reveal">
            <div class="feature-icon">🚀</div>
            <h3>Pregătire de carieră</h3>
            <p>CV tech, simulări de interviu, GitHub, LinkedIn și orientare practică spre primele oportunități în IT.</p>
          </article>
        </div>
      </div>
    </section>

    <section id="courses">
      <div class="container">
        <div class="section-title reveal">
          <span class="label">Catalog cursuri</span>
          <h2>Alege programul potrivit pentru nivelul tău</h2>
          <p>
            Fiecare card are structură completă: categorie, durată, nivel, mentor, avantaje și preț.
            Poți adapta foarte ușor conținutul pentru academie, centru educațional sau brand personal.
          </p>
        </div>

        <div class="courses-grid">
          <article class="course-card reveal">
            <div class="course-thumb">
              <div class="shape s1"></div>
              <div class="shape s2"></div>
              <div class="shape s3"></div>
            </div>
            <div class="course-header">
              <h3>Front-End Developer</h3>
              <span class="tag">Beginner</span>
            </div>
            <div class="course-meta">
              <span>12 săptămâni</span>
              <span>•</span>
              <span>HTML, CSS, JS</span>
            </div>
            <p>Înveți cum să construiești interfețe moderne, responsive și animate, de la zero până la proiect final.</p>
            <ul class="bullet-list">
              <li>Structură HTML semantică</li>
              <li>CSS modern și animații</li>
              <li>JavaScript pentru interactivitate</li>
            </ul>
            <div class="mentor-row">
              <div class="mentor">
                <div class="mentor-avatar">AD</div>
                <div>
                  <strong>Ana D.</strong>
                  <small>Mentor Front-End</small>
                </div>
              </div>
              <div class="price">149€</div>
            </div>
            <a href="#contact" class="btn">Rezervă loc</a>
          </article>

          <article class="course-card reveal">
            <div class="course-thumb">
              <div class="shape s1"></div>
              <div class="shape s2"></div>
              <div class="shape s3"></div>
            </div>
            <div class="course-header">
              <h3>Python Developer</h3>
              <span class="tag">Popular</span>
            </div>
            <div class="course-meta">
              <span>14 săptămâni</span>
              <span>•</span>
              <span>Python + logică</span>
            </div>
            <p>Curs ideal pentru cei care vor baze solide în programare, automatizare și gândire algoritmică.</p>
            <ul class="bullet-list">
              <li>Tipuri de date și structuri</li>
              <li>Funcții, fișiere, module</li>
              <li>Mini-proiecte și exerciții ghidate</li>
            </ul>
            <div class="mentor-row">
              <div class="mentor">
                <div class="mentor-avatar">MR</div>
                <div>
                  <strong>Mihai R.</strong>
                  <small>Mentor Python</small>
                </div>
              </div>
              <div class="price">169€</div>
            </div>
            <a href="#contact" class="btn">Rezervă loc</a>
          </article>

          <article class="course-card reveal">
            <div class="course-thumb">
              <div class="shape s1"></div>
              <div class="shape s2"></div>
              <div class="shape s3"></div>
            </div>
            <div class="course-header">
              <h3>UI/UX Design în Figma</h3>
              <span class="tag">Creative</span>
            </div>
            <div class="course-meta">
              <span>10 săptămâni</span>
              <span>•</span>
              <span>UI, prototipare</span>
            </div>
            <p>Construiești layout-uri, design systems, pagini responsive și prototipuri interactive pentru web și mobil.</p>
            <ul class="bullet-list">
              <li>Wireframe și ierarhie vizuală</li>
              <li>Componente și auto layout</li>
              <li>Prototipuri și cazuri practice</li>
            </ul>
            <div class="mentor-row">
              <div class="mentor">
                <div class="mentor-avatar">IK</div>
                <div>
                  <strong>Irina K.</strong>
                  <small>Mentor UI/UX</small>
                </div>
              </div>
              <div class="price">139€</div>
            </div>
            <a href="#contact" class="btn">Rezervă loc</a>
          </article>
        </div>
      </div>
    </section>

    <section class="progress-section" id="roadmap">
      <div class="container timeline-wrap">
        <div class="timeline-box reveal">
          <span class="label">Procesul de studiu</span>
          <h2 style="margin-top: 12px; margin-bottom: 12px;">Cum decurge învățarea în academie</h2>
          <p style="color: var(--muted); line-height: 1.8;">
            Flux clar pentru utilizatori noi: înscriere, evaluare de nivel, acces la platformă, mentorat și proiect final.
          </p>
          <div class="timeline">
            <div class="timeline-item">
              <h4>1. Alegi direcția</h4>
              <p>Selectezi cursul potrivit, consulți programa, nivelul, durata și rezultatele așteptate.</p>
            </div>
            <div class="timeline-item">
              <h4>2. Primești plan personalizat</h4>
              <p>Ai acces la structură pe module, recomandări de ritm și obiective clare pe săptămâni.</p>
            </div>
            <div class="timeline-item">
              <h4>3. Lucrezi practic</h4>
              <p>Fiecare modul conține aplicații, mini-teme, provocări și exerciții reale de consolidare.</p>
            </div>
            <div class="timeline-item">
              <h4>4. Construiești portofoliu</h4>
              <p>Finalizezi proiecte pe care le poți prezenta la examen, interviu sau pe profilul tău profesional.</p>
            </div>
          </div>
        </div>

        <div class="stats-box reveal">
          <div class="ring-card">
            <div class="ring"><span>78%</span></div>
            <div>
              <h3>Rată medie de finalizare</h3>
              <p>Studenții finalizează cursurile deoarece au structură clară, obiective concrete și suport constant.</p>
            </div>
          </div>
          <div class="mini-stats">
            <div class="mini-stat">
              <strong>96 ore</strong>
              <span>Material video și practică</span>
            </div>
            <div class="mini-stat">
              <strong>32</strong>
              <span>Proiecte și exerciții</span>
            </div>
            <div class="mini-stat">
              <strong>12 mentori</strong>
              <span>Specialiști activi în industrie</span>
            </div>
            <div class="mini-stat">
              <strong>24/7</strong>
              <span>Acces la platformă și resurse</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="pricing">
      <div class="container">
        <div class="section-title reveal">
          <span class="label">Prețuri</span>
          <h2>Pachete flexibile pentru diferite obiective</h2>
          <p>
            Poți folosi această secțiune pentru abonamente lunare, plăți per curs sau oferte promoționale.
          </p>
        </div>

        <div class="pricing-grid">
          <article class="pricing-card reveal">
            <h3>Starter</h3>
            <p>Perfect pentru cei care vor să înceapă cu un singur curs și suport de bază.</p>
            <div class="price-big">49<small>€/lună</small></div>
            <ul class="bullet-list">
              <li>Acces la 1 curs</li>
              <li>Fișiere și resurse</li>
              <li>Teste de evaluare</li>
            </ul>
            <a href="#contact" class="btn-outline">Alege Starter</a>
          </article>

          <article class="pricing-card popular reveal">
            <div class="popular-badge">Cel mai ales</div>
            <h3>Pro</h3>
            <p>Varianta ideală pentru studiu constant, cu mentorat și acces extins la proiecte practice.</p>
            <div class="price-big">89<small>€/lună</small></div>
            <ul class="bullet-list">
              <li>Acces la 3 cursuri</li>
              <li>Mentorat săptămânal</li>
              <li>Feedback pe proiecte</li>
              <li>Comunitate privată</li>
            </ul>
            <a href="#contact" class="btn">Alege Pro</a>
          </article>

          <article class="pricing-card reveal">
            <h3>Premium</h3>
            <p>Pachet complet pentru cei care vor progres accelerat și susținere avansată.</p>
            <div class="price-big">149<small>€/lună</small></div>
            <ul class="bullet-list">
              <li>Acces total la platformă</li>
              <li>Mentorat intensiv</li>
              <li>Revizuire portofoliu</li>
              <li>Simulări interviu</li>
            </ul>
            <a href="#contact" class="btn-outline">Alege Premium</a>
          </article>
        </div>
      </div>
    </section>

    <section id="testimonials">
      <div class="container">
        <div class="section-title reveal">
          <span class="label">Testimoniale</span>
          <h2>Ce spun cursanții despre experiența de învățare</h2>
          <p>O secțiune esențială pentru încredere, conversie și imagine profesională.</p>
        </div>

        <div class="testimonials-grid">
          <article class="testimonial-card reveal">
            <div class="stars">★★★★★</div>
            <p>Mi-a plăcut mult structura lecțiilor și faptul că fiecare temă a avut aplicabilitate reală. Mi-am făcut primul site complet după câteva săptămâni.</p>
            <div class="testimonial-user">
              <div class="testimonial-avatar">AC</div>
              <div>
                <strong>Alex C.</strong>
                <small style="color: var(--muted);">Front-End Student</small>
              </div>
            </div>
          </article>

          <article class="testimonial-card reveal">
            <div class="stars">★★★★★</div>
            <p>Platforma arată foarte modern, iar mentorii explică simplu chiar și concepte mai dificile. Proiectele m-au ajutat mult să înțeleg logica.</p>
            <div class="testimonial-user">
              <div class="testimonial-avatar">MP</div>
              <div>
                <strong>Maria P.</strong>
                <small style="color: var(--muted);">Python Student</small>
              </div>
            </div>
          </article>

          <article class="testimonial-card reveal">
            <div class="stars">★★★★★</div>
            <p>Mi-a plăcut combinația dintre design, animații și conținut clar. Totul pare premium și bine gândit, nu doar un site simplu de prezentare.</p>
            <div class="testimonial-user">
              <div class="testimonial-avatar">IR</div>
              <div>
                <strong>Irina R.</strong>
                <small style="color: var(--muted);">UI/UX Student</small>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section id="faq">
      <div class="container faq-grid">
        <div class="section-title reveal" style="margin: 0; text-align: left; max-width: 100%;">
          <span class="label">FAQ</span>
          <h2>Întrebări frecvente</h2>
          <p>
            Componentă interactivă cu deschidere/închidere, utilă pentru înscriere, plată, durată, nivel și certificare.
          </p>
        </div>

        <div class="faq-list reveal">
          <div class="faq-item active">
            <button class="faq-question">
              <span>Trebuie să am experiență anterioară în IT?</span>
              <span>+</span>
            </button>
            <div class="faq-answer">
              Pentru majoritatea cursurilor de bază, nu. Programele sunt structurate gradual și pornesc de la noțiuni fundamentale.
            </div>
          </div>
          <div class="faq-item">
            <button class="faq-question">
              <span>Primesc certificat la final?</span>
              <span>+</span>
            </button>
            <div class="faq-answer">
              Da, poți integra un certificat digital de absolvire pentru fiecare curs sau pentru traseele complete de studiu.
            </div>
          </div>
          <div class="faq-item">
            <button class="faq-question">
              <span>Pot învăța în ritmul meu?</span>
              <span>+</span>
            </button>
            <div class="faq-answer">
              Da. Poți adapta lecțiile după programul tău, iar mentoratul te ajută să rămâi pe direcția corectă.
            </div>
          </div>
          <div class="faq-item">
            <button class="faq-question">
              <span>Există proiecte practice?</span>
              <span>+</span>
            </button>
            <div class="faq-answer">
              Absolut. Site-ul este gândit în jurul ideii de practică, portofoliu și aplicabilitate reală pentru fiecare modul.
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container contact-grid">
        <div class="contact-card reveal">
          <span class="label">Contact</span>
          <h2 style="margin-top: 12px; margin-bottom: 14px;">Începe acum cu un curs IT</h2>
          <p>
            Completează formularul și personalul academic poate reveni cu informații despre programă, grupe, nivel și oferte.
          </p>
          <div class="contact-items">
            <div class="contact-item">
              <strong>Email</strong>
              <span>admitere@itacademy.md</span>
            </div>
            <div class="contact-item">
              <strong>Telefon</strong>
              <span>+373 60 123 456</span>
            </div>
            <div class="contact-item">
              <strong>Program</strong>
              <span>Luni – Sâmbătă, 09:00 – 18:00</span>
            </div>
          </div>
        </div>

        <div class="contact-card reveal">
          <h3>Formular de înscriere</h3>
          <p style="margin-bottom: 20px;">Un formular modern completează perfect single page-ul și oferă un punct clar de conversie.</p>
          <form class="contact-form" onsubmit="event.preventDefault(); showMessage();">
            <div class="field">
              <label>Nume</label>
              <input type="text" placeholder="Numele tău" required>
            </div>
            <div class="field">
              <label>Prenume</label>
              <input type="text" placeholder="Prenumele tău" required>
            </div>
            <div class="field">
              <label>Email</label>
              <input type="email" placeholder="email@exemplu.com" required>
            </div>
            <div class="field">
              <label>Telefon</label>
              <input type="tel" placeholder="+373 ...">
            </div>
            <div class="field full">
              <label>Curs dorit</label>
              <select>
                <option>Front-End Developer</option>
                <option>Python Developer</option>
                <option>UI/UX Design</option>
                <option>Data Analytics</option>
              </select>
            </div>
            <div class="field full">
              <label>Mesaj</label>
              <textarea rows="5" placeholder="Scrie aici ce te interesează..."></textarea>
            </div>
            <div class="field full">
              <button type="submit" class="btn">Trimite cererea</button>
            </div>
            <div class="field full">
              <small id="formMessage" style="color: var(--accent-2);"></small>
            </div>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer class="footer">
    <div class="container footer-grid">
      <div class="footer-col">
        <a href="#home" class="logo" style="margin-bottom: 14px; display: inline-flex;">
          <div class="logo-mark">&lt;/&gt;</div>
          <span>IT Academy</span>
        </a>
        <p>Single page modern pentru cursuri IT, cu design premium, animații diverse și structură completă de prezentare.</p>
      </div>
      <div class="footer-col">
        <h4>Meniu</h4>
        <ul class="footer-links">
          <li><a href="#features">Avantaje</a></li>
          <li><a href="#courses">Cursuri</a></li>
          <li><a href="#pricing">Prețuri</a></li>
          <li><a href="#faq">FAQ</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Domenii</h4>
        <ul class="footer-links">
          <li><a href="#courses">Web Development</a></li>
          <li><a href="#courses">Python</a></li>
          <li><a href="#courses">UI/UX Design</a></li>
          <li><a href="#courses">Data Analytics</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Contact</h4>
        <p>Email: admitere@itacademy.md</p>
        <p>Telefon: +373 60 123 456</p>
        <p>Chișinău, Moldova</p>
      </div>
    </div>
    <div class="container" style="margin-top: 28px;">
      <p class="footer-note">© 2026 IT Academy. Toate drepturile rezervate.</p>
    </div>
  </footer>

  <script>
    const menuToggle = document.getElementById('menuToggle');
    const menu = document.getElementById('menu');
    const navLinks = document.querySelectorAll('.menu a');
    const sections = document.querySelectorAll('section[id]');
    const revealEls = document.querySelectorAll('.reveal');

    menuToggle.addEventListener('click', () => {
      menu.classList.toggle('open');
      menuToggle.textContent = menu.classList.contains('open') ? '✕' : '☰';
    });

    navLinks.forEach(link => {
      link.addEventListener('click', () => {
        menu.classList.remove('open');
        menuToggle.textContent = '☰';
      });
    });

    const activateMenuOnScroll = () => {
      let current = '';
      sections.forEach(section => {
        const sectionTop = section.offsetTop - 140;
        if (window.scrollY >= sectionTop) {
          current = section.getAttribute('id');
        }
      });

      navLinks.forEach(link => {
        link.classList.remove('active');
        if (link.getAttribute('href') === `#${current}`) {
          link.classList.add('active');
        }
      });
    };

    window.addEventListener('scroll', activateMenuOnScroll);
    activateMenuOnScroll();

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, { threshold: 0.12 });

    revealEls.forEach(el => observer.observe(el));

    document.querySelectorAll('.faq-question').forEach(button => {
      button.addEventListener('click', () => {
        const item = button.parentElement;
        document.querySelectorAll('.faq-item').forEach(faq => {
          if (faq !== item) faq.classList.remove('active');
        });
        item.classList.toggle('active');
      });
    });

    function showMessage() {
      const formMessage = document.getElementById('formMessage');
      formMessage.textContent = 'Cererea a fost trimisă cu succes! În varianta reală, aici poți conecta formularul la backend sau email.';
      setTimeout(() => {
        formMessage.textContent = '';
      }, 5000);
    }
  </script>
</body>
</html>
