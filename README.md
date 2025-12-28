<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Offre Spéciale Noël 2025 - Pour Chaque Habitant !</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Arial, sans-serif;
      background: linear-gradient(135deg, #1e3c72, #2a5298);
      color: white;
      min-height: 200vh;
      position: relative;
      overflow-x: hidden;
    }

    body::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0; bottom: 0;
      background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><circle fill="%23fff" cx="20" cy="20" r="3"/><circle fill="%23fff" cx="80" cy="40" r="4"/><circle fill="%23fff" cx="50" cy="70" r="2"/><circle fill="%23fff" cx="30" cy="90" r="3"/></svg>') repeat;
      opacity: 0.3;
      animation: snow 20s linear infinite;
      pointer-events: none;
    }

    @keyframes snow {
      0% { background-position: 0 0; }
      100% { background-position: 0 1000px; }
    }

    .section {
      max-width: 900px;
      margin: 0 auto;
      padding: 40px 20px;
      text-align: center;
    }

    h1, h2 {
      text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);
    }

    h1 { font-size: 3em; margin-bottom: 20px; }
    h2 { font-size: 2.5em; margin: 40px 0 20px; }

    p {
      font-size: 1.4em;
      line-height: 1.6;
      margin: 20px 0;
    }

    .highlight { color: #ffeb3b; font-weight: bold; }

    #inscription-form {
      background: rgba(255, 255, 255, 0.2);
      padding: 30px;
      border-radius: 15px;
      max-width: 500px;
      margin: 0 auto;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
    }

    input[type="text"], input[type="email"] {
      width: 100%;
      padding: 12px;
      margin: 10px 0;
      border-radius: 5px;
      border: none;
      font-size: 1em;
    }

    /* Boutons stylés (Vérifier et Réclamer) */
    .action-btn {
      background-color: #ff4b4b;
      color: white;
      padding: 15px 30px;
      border: none;
      border-radius: 8px;
      font-size: 1.4em;
      font-weight: bold;
      cursor: pointer;
      margin-top: 30px;
      box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3);
      transition: all 0.3s ease;
      display: none; /* caché au départ */
    }

    .action-btn:hover {
      background-color: #e63939;
      transform: translateY(-3px);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.4);
    }

    #gift-container {
      cursor: pointer;
      font-size: 10em;
      animation: pulse 2s infinite;
      margin: 50px 0;
      display: none;
    }

    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }

    #offre-revelee {
      background: rgba(0, 255, 0, 0.2);
      padding: 30px;
      border-radius: 15px;
      font-size: 2.2em;
      margin: 40px auto;
      max-width: 700px;
      opacity: 0;
      transform: scale(0.8);
      transition: all 1s ease;
      display: none;
    }

    #offre-revelee.show {
      opacity: 1;
      transform: scale(1);
      display: block;
    }

    .guide-text {
      font-size: 1.8em;
      margin: 30px 0;
      opacity: 0;
      transition: opacity 0.8s ease;
    }

    .guide-text.show {
      opacity: 1;
    }

    .stars {
      position: absolute;
      top: 0; left: 0; right: 0; bottom: 0;
      pointer-events: none;
    }

    .star {
      position: absolute;
      background: white;
      border-radius: 50%;
      animation: twinkle 5s infinite;
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.3; }
      50% { opacity: 1; }
    }

    .footer {
      margin-top: 100px;
      font-size: 1.2em;
      opacity: 0.9;
    }
  </style>
</head>
<body>

  <div class="stars">
    <div class="star" style="width:4px;height:4px;top:10%;left:15%;animation-delay:0s;"></div>
    <div class="star" style="width:3px;height:3px;top:20%;left:70%;animation-delay:1s;"></div>
    <div class="star" style="width:5px;height:5px;top:30%;left:40%;animation-delay:2s;"></div>
    <div class="star" style="width:3px;height:3px;top:50%;left:85%;animation-delay:0.5s;"></div>
    <div class="star" style="width:4px;height:4px;top:70%;left:20%;animation-delay:3s;"></div>
    <div class="star" style="width:6px;height:6px;top:80%;left:60%;animation-delay:1.5s;"></div>
    <div class="star" style="width:4px;height:4px;top:90%;left:30%;animation-delay:2.5s;"></div>
    <div class="star" style="width:5px;height:5px;top:60%;left:50%;animation-delay:4s;"></div>
  </div>

  <div class="section">
    <h1>✨ Offre Spéciale Noël 2025 ✨</h1>
    <p>Bienvenue sur notre page dédiée aux fêtes de fin d'année ! Cette année, nous avons une surprise pour <span class="highlight">chaque habitant</span> de notre communauté.</p>
    <p>Que vous soyez jeune ou senior, du centre-ville ou des quartiers périphériques, Noël 2025 sera magique pour tous !</p>
  </div>

  <div class="section">
    <h2>Une Offre Exceptionnelle Pour Tous</h2>
    <p>À l'occasion de Noël, nous offrons un <span class="highlight">cadeau personnalisé</span> à chaque résident. Pas de tirage au sort, pas de conditions compliquées : c'est pour <strong>tout le monde</strong> !</p>
    <p>Imaginez : un bonus festif qui illuminera vos fêtes. Inscrivez-vous ci-dessous pour découvrir votre offre exclusive.</p>
    <p>Pourquoi cette offre ? Parce que Noël est synonyme de partage, et nous voulons que chaque habitant se sente spécial en cette période magique.</p>
  </div>

  <div class="section">
    <!-- Titre dynamique -->
    <h2 id="section-title">Inscrivez-vous pour Participer</h2>

    <!-- Texte guide pour le cadeau -->
    <p id="guide-text" class="guide-text"></p>

    <form id="inscription-form">
      <input type="text" id="nom" placeholder="Votre Nom" required>
      <input type="email" id="email" placeholder="Votre Email" required>
      <button type="submit">S'inscrire</button>
    </form>

    <button id="verifier-offre-btn" class="action-btn">Vérifier Mon Offre Pour Noël</button>

    <div id="gift-container">🎁</div>

    <div id="offre-revelee"></div>

    <button id="reclamer-btn" class="action-btn">Réclamer Mon Offre</button>
  </div>

  <div class="section">
    <h2>Pourquoi Cette Offre Est Unique</h2>
    <p>Notre offre est conçue pour apporter de la joie à tous les habitants. Que ce soit un chèque-cadeau, une réduction exclusive ou un surprise personnalisée, tout est pensé pour vous !</p>
    <p>Rejoignez des milliers d'autres résidents qui ont déjà profité de cette initiative festive. Noël 2025 sera inoubliable !</p>
  </div>

  <div class="footer section">
    🎄 Toute l'équipe vous souhaite de joyeuses fêtes ! 🎄<br>
    Contact : contact@offrenoel2025.fr
  </div>

  <script>
    const form = document.getElementById('inscription-form');
    const sectionTitle = document.getElementById('section-title');
    const guideText = document.getElementById('guide-text');
    const verifierBtn = document.getElementById('verifier-offre-btn');
    const giftContainer = document.getElementById('gift-container');
    const offreRevelee = document.getElementById('offre-revelee');
    const reclamerBtn = document.getElementById('reclamer-btn');

    form.addEventListener('submit', (e) => {
      e.preventDefault();
      const nom = document.getElementById('nom').value;
      const email = document.getElementById('email').value;

      if (nom && email) {
        alert(`Inscription réussie pour ${nom} (${email}) !`);
        form.style.display = 'none';
        sectionTitle.style.display = 'none'; // Le titre "Inscrivez-vous..." disparaît
        verifierBtn.style.display = 'inline-block';
      }
    });

    verifierBtn.addEventListener('click', () => {
      verifierBtn.style.display = 'none';
      guideText.textContent = 'Touchez le cadeau pour découvrir votre offre';
      guideText.classList.add('show');
      giftContainer.style.display = 'block';
    });

    giftContainer.addEventListener('click', () => {
      // 1. Faire disparaître le cadeau lentement
      giftContainer.style.transition = 'opacity 1s ease';
      giftContainer.style.opacity = '0';

      setTimeout(() => {
        giftContainer.style.display = 'none';

        // 2. Générer le prix (biaisé vers 550€)
        const prix = [300, 400, 550, 600];
        const random = Math.random();
        let offre;
        if (random < 0.7) offre = 550;
        else if (random < 0.8) offre = 300;
        else if (random < 0.9) offre = 400;
        else offre = 600;

        offreRevelee.innerHTML = `Félicitations ! Votre offre Noël est de <span class="highlight">${offre} €</span> !`;
        offreRevelee.style.display = 'block';

        // 3. Animation d'apparition lente et jolie
        setTimeout(() => {
          offreRevelee.classList.add('show');
          reclamerBtn.style.display = 'inline-block';
        }, 300);
      }, 1000); // Attendre la fin du fade out
    });

    reclamerBtn.addEventListener('click', () => {
      alert('Votre offre a été réclamée avec succès ! Un email de confirmation vous sera envoyé.');
    });
  </script>
</body>
</html>
