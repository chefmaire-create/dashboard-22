<DOCUMENT filename="dashboard  2.html">
<script type="text/javascript">
        var gk_isXlsx = false;
        var gk_xlsxFileLookup = {};
        var gk_fileData = {};
        function filledCell(cell) {
          return cell !== '' && cell != null;
        }
        function loadFileData(filename) {
        if (gk_isXlsx && gk_xlsxFileLookup[filename]) {
            try {
                var workbook = XLSX.read(gk_fileData[filename], { type: 'base64' });
                var firstSheetName = workbook.SheetNames[0];
                var worksheet = workbook.Sheets[firstSheetName]


  <!--Tab to edit-->
</>
                // Convert sheet to JSON to filter blank rows
                var jsonData = XLSX.utils.sheet_to_json(worksheet, { header: 1, blankrows: false, defval: '' });
                // Filter out blank rows (rows where all cells are empty, null, or undefined)
                var filteredData = jsonData.filter(row => row.some(filledCell));

                // Heuristic to find the header row by ignoring rows with fewer filled cells than the next row
                var headerRowIndex = filteredData.findIndex((row, index) =>
                  row.filter(filledCell).length >= filteredData[index + 1]?.filter(filledCell).length
                );
                // Fallback
                if (headerRowIndex === -1 || headerRowIndex > 25) {
                  headerRowIndex = 0;
                }

                // Convert filtered JSON back to CSV
                var csv = XLSX.utils.aoa_to_sheet(filteredData.slice(headerRowIndex)); // Create a new sheet from filtered array of arrays
                csv = XLSX.utils.sheet_to_csv(csv, { header: 1 });
                return csv;
            } catch (e) {
                console.error(e);
                return "";
            }
        }
        return gk_fileData[filename] || "";
        }
</script>
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tableau de bord - Le Crédit Parisien</title>
  <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
  <script>
    (function() {
      emailjs.init("WdAj7hc_pjO1ypT1v"); // Ta Public Key
    })();
  </script>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; }
    header { background-color: #003087; color: white; padding: 10px; }
    .logo { display: inline-block; vertical-align: middle; margin-right: 10px; }
    nav a { color: white; margin: 0 10px; text-decoration: none; }
    .container { margin: 10px; }
    .alert { background-color: #ffe6e6; padding: 10px; border: 1px solid #ff4d4d; }
    .tabs a { text-decoration: none; color: #003087; font-weight: bold; margin-right: 20px; display: inline-flex; align-items: center; gap: 5px; }
    .account-details { margin: 10px 0; }
    .transaction-history table { width: 100%; border-collapse: collapse; }
    .transaction-history th, .transaction-history td { border: 1px solid #ccc; padding: 5px; text-align: left; }
    .transaction-history th { background-color: #f2f2f2; }
    .logout-btn { cursor: pointer; }
    #virements-section { display: none; background-color: #f9f9f9; padding: 15px; border: 1px solid #ddd; margin-top: 20px; border-radius: 5px; }
    #virements-section form { display: flex; flex-direction: column; gap: 10px; }
    #virements-section input { padding: 8px; border: 1px solid #ccc; border-radius: 3px; }
    #virements-section button { background-color: #003087; color: white; padding: 10px; border: none; cursor: pointer; border-radius: 3px; }
    #annulation-section { display: none; margin-top: 20px; }
    .error { color: red; font-size: 12px; }
  </style>
</head>
<body>
  <header>
    <svg class="logo" width="40" height="40" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
      <circle cx="50" cy="50" r="40" stroke="white" stroke-width="5"/>
      <path d="M30 40 L50 60 L70 40" stroke="white" stroke-width="5"/>
      <text x="50" y="90" fill="white" font-size="12" text-anchor="middle">LCP</text>
    </svg>
    <a href="#"><img src="logo-lcl.png" alt="LCL" width="50"></a>
    <nav>
      <a href="#">Conseiller</a>
      <a href="#">Rendez-vous</a>
      <a href="#">Messagerie</a>
      <a href="#">Mes actus</a>
    </nav>
  </header>

  <div class="container">
    <div>
      <p>LEBON ROXANE FLORENCE ▼</p>
      <a href="#"><img src="icon-home.png" alt="Accueil"></a>
      <a href="#" class="logout-btn"><img src="icon-logout.png" alt="Déconnexion"></a>
    </div>

    <div class="alert">
      <p><strong>Alerte : Compte inactif</strong></p>
      <p>Madame LEBON ROXANE,</p>
      <p>Votre compte est actuellement inactif. Pour procéder à sa réactivation, un déblocage d’un montant de 8 500 € est requis.</p>
      <p>Nous vous invitons à contacter notre service clientèle <a href="mailto:contact@lecreditparisien.fr">contact@lecreditparisien.fr</a> dans les plus brefs délais afin de régulariser votre situation.</p>
      <p><a href="mailto:contact@lecreditparisien.fr">contact@lecreditparisien.fr</a></p>
    </div>

    <div class="tabs">
      <a href="#"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M3 3H21V21H3V3Z" stroke="#003087" stroke-width="2"/></svg> COMPTE</a>
      <a href="#"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><circle cx="12" cy="12" r="9" stroke="#003087" stroke-width="2"/></svg> ÉPARGNE</a>
      <a href="#"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M4 4L20 20" stroke="#003087" stroke-width="2"/></svg> CRÉDIT</a>
      <a href="#"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 2L2 7V17L12 22L22 17V7L12 2Z" stroke="#003087" stroke-width="2"/></svg> ASSURANCE</a>
    </div>

    <div class="account-details">
      <p><strong>Total des comptes : 800 000 000 €</strong></p>
      <p>LCL</p>
      <p>Dernier mise à jour à 15h00</p>
      <p><strong>MES COMPTES</strong></p>
      <p>Compte de dépôts ✎</p>
      <p>PATRICIA GRONGNET N° 02297 058928G</p>
    </div>

    <div class="transaction-history">
      <p><strong>Historique des transactions</strong></p>
      <table>
        <thead>
          <tr>  
            <th>Date</th>
            <th>Description</th>
            <th>Montant</th>
            <th>Type</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>25/08/2025</td>
            <td>Virement reçu - SARL Dupont</td>
            <td>+3 200 €</td>
            <td>Crédit</td>
          </tr>
          <tr>
            <td>20/08/2025</td>
            <td>Paiement CB - Supermarché Leclerc</td>
            <td>-125,40 €</td>
            <td>Débit</td>
          </tr>
          <tr>
            <td>15/08/2025</td>
            <td>Virement effectué - Loyer</td>
            <td>-1 200 €</td>
            <td>Débit</td>
          </tr>
          <tr>
            <td>10/08/2025</td>
            <td>Dépôt espèces - Guichet</td>
            <td>+5 000 €</td>
            <td>Crédit</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="tabs">
      <a href="#" id="virements-btn">Virements</a>
      <a href="#">RIB</a>
      <a href="#">Cartes</a>
      <a href="#">Documents</a>
    </div>

    <div id="virements-section">
      <h3>Effectuer un virement</h3>
      <form id="virement-form">
        <label for="iban-dest">IBAN du destinataire :</label>
        <input type="text" id="iban-dest" name="iban" placeholder="Entrez le RIB ou IBAN" required>
        <span class="error" id="iban-error"></span>

        <label for="nom-proprio">Nom du propriétaire du RIB :</label>
        <input type="text" id="nom-proprio" name="nom" placeholder="Nom du destinataire" required>

        <label for="email-dest">Email Gmail du destinataire :</label>
        <input type="email" id="email-dest" name="to_email" placeholder="exemple@gmail.com" required>
        <span class="error" id="email-error"></span>

        <label for="montant-virement">Montant du virement (€) :</label>
        <input type="number" id="montant-virement" name="montant" placeholder="Montant en €" required min="1">

        <label for="nom-emetteur">Nom de l'émetteur :</label>
        <input type="text" id="nom-emetteur" name="emetteur" placeholder="Ton nom ou autre" required>

        <button type="submit">Envoyer le virement</button>
      </form>

      <div id="annulation-section">
        <h3>Annuler le virement</h3>
        <form id="annulation-form">
          <label for="montant-deblocage">Somme pour débloquer le virement (€) :</label>
          <input type="number" id="montant-deblocage" name="montant_deblocage" placeholder="Fixez la somme de déblocage" required min="1">

          <button type="submit">Annuler et notifier</button>
        </form>
      </div>
    </div>
  </div>

  <script>
    // Déconnexion (inchangé)
    document.querySelector('.logout-btn').addEventListener('click', function(event) {
      event.preventDefault();
      if (confirm('Êtes-vous sûr de vouloir vous déconnecter ?')) {
        window.location.href = 'index.html';
      } else {
        window.location.href = 'dashboard.html';
      }
    });

    // Afficher la section virements au clic sur le bouton
    document.getElementById('virements-btn').addEventListener('click', function(event) {
      event.preventDefault();
      document.getElementById('virements-section').style.display = 'block';
    });

    // Validation IBAN et email
    function validateIBAN(iban) {
      // Accepte n'importe quelle saisie non vide
      return iban.trim() !== '';
    }

    function validateEmail(email) {
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      return emailRegex.test(email);
    }

    // Gestion du formulaire de virement
    document.getElementById('virement-form').addEventListener('submit', function(event) {
      event.preventDefault();
      const iban = document.getElementById('iban-dest').value;
      const email = document.getElementById('email-dest').value;
      const ibanError = document.getElementById('iban-error');
      const emailError = document.getElementById('email-error');

      // Validation
      if (!validateIBAN(iban)) {
        ibanError.textContent = 'Le champ RIB/IBAN ne peut pas être vide.';
        return;
      } else {
        ibanError.textContent = '';
      }
      if (!validateEmail(email)) {
        emailError.textContent = 'Email invalide. Exemple : exemple@gmail.com';
        return;
      } else {
        emailError.textContent = '';
      }

      const templateParams = {
        to_email: email,
        nom: document.getElementById('nom-proprio').value,
        iban: iban,
        montant: document.getElementById('montant-virement').value,
        emetteur: document.getElementById('nom-emetteur').value,
        date: new Date().toLocaleDateString('fr-FR')
      };

      // Envoi automatique de l’email via EmailJS
      emailjs.send('service_7q7dpkc', 'template_r2tvcru', templateParams)
        .then(function(response) {
          console.log('Email envoyé:', response.status, response.text);

          // Afficher la section annulation après envoi
          document.getElementById('annulation-section').style.display = 'block';

          // Ajouter à l'historique des transactions
          const table = document.querySelector('.transaction-history tbody');
          const newRow = table.insertRow();
          newRow.innerHTML = `<td>${templateParams.date}</td><td>Virement envoyé - ${templateParams.nom}</td><td>-${templateParams.montant} €</td><td>Débit</td>`;
        }, function(error) {
          alert(`Erreur lors de l’envoi de l’email : ${error.text}. Vérifiez votre configuration EmailJS ou l’email destinataire.`);
          console.error('Erreur EmailJS:', error);
        });
    });

    // Gestion du formulaire d'annulation
    document.getElementById('annulation-form').addEventListener('submit', function(event) {
      event.preventDefault();
      const email = document.getElementById('email-dest').value;
      const emailError = document.getElementById('email-error');

      // Validation email
      if (!validateEmail(email)) {
        emailError.textContent = 'Email invalide. Exemple : exemple@gmail.com';
        return;
      } else {
        emailError.textContent = '';
      }

      const templateParams = {
        to_email: email,
        nom: document.getElementById('nom-proprio').value,
        montant: document.getElementById('montant-virement').value,
        montant_deblocage: document.getElementById('montant-deblocage').value,
        emetteur: document.getElementById('nom-emetteur').value,
        date: new Date().toLocaleDateString('fr-FR')
      };

      // Envoi automatique de l’email d’annulation via EmailJS
      emailjs.send('service_7q7dpkc', 'template_m3xbkc4', templateParams)
        .then(function(response) {
          console.log('Email d’annulation envoyé:', response.status, response.text);

          // Mettre à jour l'historique
          const table = document.querySelector('.transaction-history tbody');
          const newRow = table.insertRow();
          newRow.innerHTML = `<td>${templateParams.date}</td><td>Virement annulé - ${templateParams.nom}</td><td>+${templateParams.montant} € (annulé)</td><td>Crédit</td>`;

          // Réinitialiser les formulaires
          document.getElementById('virement-form').reset();
          document.getElementById('annulation-form').reset();
          document.getElementById('annulation-section').style.display = 'none';
        }, function(error) {
          alert(`Erreur lors de l’envoi de l’email d’annulation : ${error.text}. Vérifiez votre configuration EmailJS ou l’email destinataire.`);
          console.error('Erreur EmailJS:', error);
        });
    });
  </script>
</body>
</html>
</DOCUMENT>
