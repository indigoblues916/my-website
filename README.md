html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Chronicology | Full Custom Catalog, Kicks, Home & UV Lounge</title>
  <link rel="preconnect" href="https://googleapis.com">
  <link rel="preconnect" href="https://gstatic.com" crossorigin>
  <link href="https://googleapis.com/css2?family=Cinzel+Decorative:wght@700;900&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: 'Plus Jakarta Sans', -apple-system, BlinkMacSystemFont, sans-serif;
      background-color: #090518;
      color: #ffffff;
      min-height: 100vh;
      padding-bottom: 115px;
      overflow-x: hidden;
      -webkit-font-smoothing: antialiased;
    }

    #uvLivingCanvas {
      position: fixed;
      top: 0; left: 0;
      width: 100vw; height: 100vh;
      z-index: 0;
      pointer-events: none;
    }

    .floating-art {
      position: fixed;
      pointer-events: none;
      z-index: 1;
      opacity: 0.24;
      filter: drop-shadow(0 0 24px rgba(57, 255, 20, 0.65)) drop-shadow(0 0 38px rgba(15, 82, 186, 0.75));
      animation: floatDream 9s ease-in-out infinite alternate;
    }
    .art-1 { top: 95px; left: 2%; width: 140px; }
    .art-2 { top: 40%; right: 2%; width: 150px; animation-delay: 2s; }
    .art-3 { bottom: 115px; left: 3%; width: 130px; animation-delay: 4s; }

    @keyframes floatDream {
      0% { transform: translateY(0px) rotate(-7deg) scale(1); }
      100% { transform: translateY(-20px) rotate(7deg) scale(1.07); }
    }

    .chancery-ombre {
      font-family: 'Cinzel Decorative', 'Apple Chancery', cursive, serif;
      background: linear-gradient(90deg, #39ff14 0%, #ffd700 22%, #ff8c00 44%, #ff2a85 66%, #00b4ff 84%, #b829ff 100%);
      background-size: 220% auto;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: ombreFlow 7s linear infinite;
      filter: drop-shadow(0 4px 18px rgba(0, 180, 255, 0.45));
    }
    @keyframes ombreFlow {
      0% { background-position: 0% center; }
      100% { background-position: 220% center; }
    }

    .drip-header-wrap { position: relative; z-index: 4; }
    .marquee-wrap {
      background: linear-gradient(90deg, #100829, #0c2247, #1c0b3d, #0d2b1d, #100829);
      color: #ffffff;
      font-size: 0.8rem;
      font-weight: 700;
      padding: 11px 0;
      overflow: hidden;
      white-space: nowrap;
      text-transform: uppercase;
      letter-spacing: 2px;
    }
    .marquee-text {
      display: inline-block;
      animation: scrollBanner 30s linear infinite;
    }
    @keyframes scrollBanner {
      0% { transform: translateX(100vw); }
      100% { transform: translateX(-100%); }
    }
    .liquid-drip-svg {
      display: block;
      width: 100%;
      height: 26px;
      filter: drop-shadow(0 6px 14px rgba(57, 255, 20, 0.55));
    }

    header {
      text-align: center;
      padding: 26px 20px 22px;
      position: relative;
      z-index: 3;
    }
    .crest-3d {
      width: 112px; height: 112px;
      margin: 0 auto 14px;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 30%, rgba(255, 215, 0, 0.3), rgba(15, 82, 186, 0.4) 55%, rgba(12, 5, 28, 0.95));
      border: 2px solid #ffd700;
      box-shadow: 0 0 38px rgba(57, 255, 20, 0.45), 0 0 55px rgba(0, 180, 255, 0.4);
      display: flex; align-items: center; justify-content: center;
    }
    .crest-3d svg { width: 68px; height: 68px; }

    h1 {
      font-size: clamp(2.4rem, 6vw, 4.3rem);
      font-weight: 900;
      margin-bottom: 10px;
      letter-spacing: 2px;
    }
    .mantra-ribbon {
      display: inline-block;
      background: linear-gradient(90deg, rgba(57, 255, 20, 0.14), rgba(255, 215, 0, 0.18), rgba(0, 180, 255, 0.18), rgba(255, 42, 133, 0.14));
      border: 1px solid rgba(255, 215, 0, 0.55);
      padding: 8px 22px;
      border-radius: 50px;
      font-size: 0.88rem;
      font-weight: 700;
      color: #fff6d6;
      margin-bottom: 14px;
    }
    p.subtitle {
      color: #e8e2fa;
      font-size: 1.04rem;
      max-width: 750px;
      margin: 0 auto 20px;
      line-height: 1.6;
    }

    .daily-hub {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      align-items: center;
      gap: 12px;
    }
    .vault-pill {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: linear-gradient(135deg, rgba(15, 82, 186, 0.35), rgba(184, 41, 255, 0.28));
      border: 1px solid #00b4ff;
      color: #ffffff;
      padding: 10px 20px;
      border-radius: 50px;
      font-size: 0.9rem;
      font-weight: 700;
      backdrop-filter: blur(12px);
    }

    .section-title {
      text-align: center;
      font-size: clamp(1.7rem, 3.6vw, 2.45rem);
      margin: 38px 0 20px;
      letter-spacing: 1.5px;
      position: relative;
      z-index: 3;
    }

    .container {
      max-width: 1260px;
      margin: 0 auto 45px;
      padding: 0 22px;
      position: relative;
      z-index: 3;
    }
    .glass-3d {
      background: linear-gradient(155deg, rgba(22, 14, 54, 0.85), rgba(10, 20, 36, 0.92));
      border: 1px solid rgba(255, 215, 0, 0.35);
      border-top: 2px solid rgba(57, 255, 20, 0.65);
      border-bottom: 3px solid rgba(0, 180, 255, 0.7);
      border-radius: 24px;
      padding: 24px;
      box-shadow: 0 22px 45px rgba(0, 0, 0, 0.65);
      backdrop-filter: blur(18px);
      transition: transform 0.25s ease, box-shadow 0.25s ease;
    }
    .glass-3d:hover {
      transform: translateY(-4px);
      box-shadow: 0 28px 55px rgba(0, 0, 0, 0.75), 0 0 40px rgba(255, 215, 0, 0.3);
    }

    .btn-uv {
      background: linear-gradient(135deg, #39ff14, #00b4ff);
      color: #060312;
      border: none;
      padding: 10px 18px;
      font-size: 0.85rem;
      font-weight: 800;
      border-radius: 50px;
      cursor: pointer;
      margin: 4px;
      box-shadow: 0 6px 20px rgba(0, 180, 255, 0.4);
      transition: all 0.2s ease;
    }
    .btn-uv:hover { transform: translateY(-2px) scale(1.03); }
    .btn-gold-bling {
      background: linear-gradient(135deg, #ffd700, #ff8c00, #ff2a85);
      color: #ffffff;
      text-shadow: 0 1px 3px rgba(0,0,0,0.5);
    }

    /* Search & Department Filter Bar */
    .catalog-controls {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 14px;
      margin-bottom: 26px;
    }
    .search-input {
      width: 100%;
      max-width: 480px;
      padding: 12px 20px;
      border-radius: 50px;
      border: 1px solid #ffd700;
      background: rgba(12, 7, 32, 0.9);
      color: #ffffff;
      font-size: 0.95rem;
      text-align: center;
      box-shadow: 0 0 20px rgba(255, 215, 0, 0.25);
    }
    .dept-tabs {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 9px;
    }
    .tab-btn {
      background: rgba(15, 82, 186, 0.28);
      border: 1px solid rgba(255, 215, 0, 0.5);
      color: #ffffff;
      padding: 8px 16px;
      border-radius: 50px;
      font-weight: 700;
      font-size: 0.83rem;
      cursor: pointer;
      transition: all 0.2s;
    }
    .tab-btn.active, .tab-btn:hover {
      background: linear-gradient(90deg, #39ff14, #ffd700, #ff2a85);
      color: #070312;
      border-color: transparent;
    }

    /* Infinite Store Grid */
    .store-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(275px, 1fr));
      gap: 24px;
    }
    .product-card {
      text-align: center;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .product-photo-wrap {
      height: 245px;
      border-radius: 18px;
      margin-bottom: 14px;
      background: radial-gradient(circle, rgba(255,255,255,0.08), rgba(9,5,24,0.9));
      border: 1px solid rgba(255, 215, 0, 0.45);
      position: relative;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: zoom-in;
    }
    .product-photo-wrap img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.35s ease;
    }
    .product-card:hover .product-photo-wrap img { transform: scale(1.06); }
    .dept-tag {
      position: absolute;
      top: 10px;
      left: 10px;
      background: rgba(9, 5, 24, 0.88);
      border: 1px solid #ffd700;
      color: #ffd700;
      font-size: 0.72rem;
      font-weight: 700;
      padding: 4px 11px;
      border-radius: 50px;
      z-index: 2;
    }
    .price-tag {
      font-size: 1.25rem;
      font-weight: 800;
      color: #ffd700;
      margin: 8px 0 10px;
    }

    /* Live Add-More-Designs Drop Box */
    .designer-drop-panel {
      margin-top: 32px;
      border: 2px dashed #39ff14;
      text-align: center;
    }
    .drop-form-row {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 12px;
      margin: 16px 0;
    }
    .drop-form-row input, .drop-form-row select {
      padding: 11px 14px;
      border-radius: 12px;
      border: 1px solid #00b4ff;
      background: rgba(11, 7, 28, 0.92);
      color: #ffffff;
      font-size: 0.9rem;
    }

    /* Fullscreen Zoom Lightbox */
    .lightbox-modal {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(6, 3, 18, 0.92);
      z-index: 100;
      align-items: center;
      justify-content: center;
      padding: 24px;
      backdrop-filter: blur(12px);
    }
    .lightbox-content {
      max-width: 560px;
      width: 100%;
      text-align: center;
    }
    .lightbox-content img {
      width: 100%;
      max-height: 65vh;
      object-fit: contain;
      border-radius: 20px;
      border: 2px solid #ffd700;
      margin-bottom: 14px;
    }

    /* Customizer Studio */
    .customizer-grid {
      display: grid;
Use code with caution.
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
gap: 26px;
align-items: center;
}
.preview-stage {
height: 310px;
border-radius: 22px;
background: radial-gradient(circle, #181c4b, #090518);
border: 2px solid #ffd700;
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
padding: 20px;
text-align: center;
}
#customPreviewImg {
max-width: 140px; max-height: 140px;
border-radius: 14px;
margin-bottom: 12px;
display: none;
box-shadow: 0 0 25px rgba(57, 255, 20, 0.65);
}
.custom-controls label {
display: block;
text-align: left;
font-size: 0.85rem;
font-weight: 700;
color: #ffd700;
margin: 12px 0 6px;
}
.custom-controls select, .custom-controls input[type="text"], .custom-controls input[type="file"] {
width: 100%;
padding: 11px 14px;
border-radius: 12px;
border: 1px solid rgba(0, 180, 255, 0.65);
background: rgba(11, 7, 28, 0.92);
color: #ffffff;
font-size: 0.92rem;
}
/* Arcade */
.arcade-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(330px, 1fr));
gap: 24px;
}
.game-card { text-align: center; }
.game-card h3 {
font-family: 'Cinzel Decorative', cursive, serif;
font-size: 1.3rem;
margin-bottom: 10px;
}
.stat-badge {
display: inline-block;
background: rgba(15, 82, 186, 0.32);
border: 1px solid #00b4ff;
padding: 5px 14px;
border-radius: 50px;
font-weight: 700;
color: #bae6fd;
margin: 0 4px 12px;
font-size: 0.82rem;
}
.mahjong-board {
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 9px;
max-width: 310px;
margin: 10px auto 16px;
}
.bling-tile {
height: 64px;
background: linear-gradient(145deg, #1b174a, #0e0a2b);
border: 1px solid #ffd700;
border-bottom: 4px solid #00b4ff;
border-radius: 14px;
display: flex; align-items: center; justify-content: center;
cursor: pointer;
}
.bling-tile svg { width: 34px; height: 34px; }
.bling-tile.selected { border-color: #39ff14; box-shadow: 0 0 22px #39ff14; transform: scale(1.07); }
.bling-tile.matched { opacity: 0.15; pointer-events: none; }
canvas.game-canvas {
background: radial-gradient(circle at center, #141842, #070414);
border: 1px solid rgba(255, 215, 0, 0.55);
border-radius: 16px;
display: block;
margin: 10px auto 14px;
width: 300px; height: 240px;
}
/* Bottom Audio Bar */
.music-bar {
position: fixed;
bottom: 0; left: 0;
width: 100%;
background: rgba(10, 6, 26, 0.95);
border-top: 2px solid #ffd700;
padding: 14px 28px;
display: flex;
justify-content: space-between;
align-items: center;
backdrop-filter: blur(18px);
z-index: 30;
}
.track-info {
font-size: 0.9rem;
font-weight: 700;
color: #ffd700;
display: flex; align-items: center; gap: 10px;
}
.controls button {
background: rgba(15, 82, 186, 0.35);
color: #ffffff;
border: 1px solid #39ff14;
padding: 8px 16px;
margin-left: 8px;
border-radius: 50px;
cursor: pointer;
font-size: 0.82rem;
font-weight: 700;
}
.controls button:hover { background: #ffd700; color: #070312; border-color: #ffd700; }


🌿 CHRONICOLOGY ORIGINAL DESIGNS • BE YOURSELF • LOVE YOURSELF • LOVE THE WORLD • BE KIND • BE GREAT • HUNDREDS OF CUSTOM PIECES & DAILY DROPS 🌿
