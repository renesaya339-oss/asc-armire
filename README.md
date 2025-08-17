# asc-armire
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ASC ARMIRE</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f5f5f5; margin:0; padding:0; color:#333; }
    header { background:#6a0dad; color:#fff; padding:20px; text-align:center; }
    header h1 { margin:0; font-size:2em; }
    header p { margin:5px 0 0 0; font-style:italic; }
    .container { max-width:900px; margin:20px auto; padding:0 20px; }
    .club-image { text-align:center; margin:20px 0; }
    .club-image img { max-width:100%; border-radius:10px; }
    section { background:#4169E1; padding:15px 20px; margin-bottom:20px; border-radius:10px; box-shadow:0 2px 5px rgba(0,0,0,0.1); }
    section h2 { color:#6a0dad; margin-top:0; }
    .actus-item, .match-item { margin-bottom:15px; }
    .partenaires a { display:inline-block; background:##32CD32; color:#fff; padding:5px 10px; margin:5px; text-decoration:none; border-radius:5px; }
  </style>
</head>
<body>

  <header>
    <h1 id="club-name">ASC ARMIRE</h1>
    <p id="club-slogan">Le club qui fait vibrer le terrain ⚽</p>
  </header>

  <div class="container">
    <div class="club-image">
      <img id="club-image" src="EC0440A2-C4AA-4625-9427-955CB0D53A3C.jpeg" alt="Équipe ASC ARMIRE">
    </div>

    <section>
      <h2>Actualités</h2>
      <div id="actus-list"></div>
    </section>

    <section>
      <h2>Prochain Match</h2>
      <div id="match-list"></div>
    </section>

    <section>
      <h2>Partenaires</h2>
      <div id="partenaires-list"></div>
    </section>
  </div>

  <script>
    // JSON du club
    const clubData = {
      "club": {
        "nom": "ASC ARMIRE",
        "slogan": "Le club qui fait vibrer le terrain ⚽",
        "adresse": "Maison de quartier Cité Arc-en-Ciel, Remire-Montjoly",
        "email": "contact@ascarmire.com",
        "image_equipe": "EC0440A2-C4AA-4625-9427-955CB0D53A3C.jpeg",
        "saison": "2025-2026"
      },
      "actus": [
        { "titre": "Victoire 2-1 contre le Géldare de Kourou", "date": "16/08/2025", "contenu": "Nos joueurs ont montré une belle performance !" },
        { "titre": "Tournoi des Jeunes", "date": "20/08/2025", "contenu": "Les U15 participent au tournoi régional." }
      ],
      "matchs": [
        { "date": "23/08/2025", "adversaire": "ACADÉMIE F.C 1", "lieu": "Stade Edmard Lama" }
      ],
      "partenaires": [
        { "nom": "Supermarché", "lien": "#" },
        { "nom": "", "lien": "#" }
      ]
    };

    // Affichage du club
    document.getElementById('club-name').innerText = clubData.club.nom;
    document.getElementById('club-slogan').innerText = clubData.club.slogan;
    document.getElementById('club-image').src = clubData.club.image_equipe;

    // Affichage des actualités
    const actusList = document.getElementById('actus-list');
    clubData.actus.forEach(actu => {
      const div = document.createElement('div');
      div.className = 'actus-item';
      div.innerHTML = <strong>${actu.date} - ${actu.titre}</strong><p>${actu.contenu}</p>;
      actusList.appendChild(div);
    });

    // Affichage du prochain match
    const matchList = document.getElementById('match-list');
    clubData.matchs.forEach(match => {
      const div = document.createElement('div');
      div.className = 'match-item';
      div.innerHTML = <strong>${match.date} - ${match.adversaire}</strong><p>Lieu : ${match.lieu}</p>;
      matchList.appendChild(div);
    });

    // Affichage des partenaires
    const partenairesList = document.getElementById('partenaires-list');
    clubData.partenaires.forEach(partenaire => {
      if(partenaire.nom) {
        const a = document.createElement('a');
        a.href = partenaire.lien;
        a.innerText = partenaire.nom;
        partenairesList.appendChild(a);
      }
    });
  </script>

</body>
</html>
