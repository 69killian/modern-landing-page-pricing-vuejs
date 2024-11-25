<template >

<div class="ellipse ellipse-center"></div>
<div class="ellipse ellipse-left"></div>

<div class="center-content">
  <div class="offer-button">
    Nos offres
  </div>

  <div class="title">Des prix en accord avec <span class="blue-title"><br/>notre vision</span></div>

  <div>
  <div>Paiement Mensuel</div>
  <div>Paiement Annuel (-20%)</div>
  </div>


  <div class="card1">
    <img src="" alt="">
    <div>Essentiel</div>
    <div>$179/month</div>

    <div><img src="" alt=""> +2500 vues/mois</div>
    <div><img src="" alt=""> +60 clics sur votre site</div>
    <div><img src="" alt=""> +15 appels/mois</div>
    <div><img src="" alt=""> +15 demandes d'itinéraires</div>
    <div><img src="" alt=""> Plus de visibilité sur Google</div>
    <div>Réponse aux avis Google inclus</div>

    <button>je m'abonne</button>
  </div>

  <div class="card2">
    <img src="" alt="">
    <div>Ultime</div>
    <div>$439/month</div>

    <div><img src="" alt=""> +6500 vues/mois</div>
    <div><img src="" alt=""> +200 clics sur votre site</div>
    <div><img src="" alt=""> +40 appels/mois</div>
    <div><img src="" alt=""> +40 demandes d'itinéraires</div>
    <div><img src="" alt=""> Plus de visibilité sur Google</div>
    <div>Réponse aux avis Google inclus</div>
    <div>1 shooting</div>
    <div>QR code personnalisé</div>

    <button>je m'abonne</button>
  </div>

  <div class="card3">
    <img src="" alt="">
    <div>Premium</div>
    <div>$319/month</div>

    <div><img src="" alt=""> +11 000 vues/mois</div>
    <div><img src="" alt=""> +500 clics sur votre site</div>
    <div><img src="" alt=""> +80 appels/mois</div>
    <div><img src="" alt=""> +80 demandes d'itinéraires</div>
    <div><img src="" alt=""> Plus de visibilité sur Google</div>
    <div>Réponse aux avis Google inclus</div>
    <div>1 shooting</div>

    <button>je m'abonne</button>
  </div>

</div>


</template>


<script>
export default {
  
}
</script>


<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;700&display=swap');

* {
  margin: 0;
  color: white;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Space Grotesk', sans-serif;
  background-color: #010B25;
}

.center-content {
  display: flex; /* Active Flexbox */
  flex-direction: column; /* Aligne les éléments verticalement */
  align-items: center; /* Centre horizontalement */
  justify-content: center; /* Centre verticalement */
  text-align: center; /* Centre le texte */
  min-height: 100vh; /* Prend toute la hauteur de la page */
  gap: 20px; /* Espace entre les éléments */
}

.card1, .card2, .card3 {
  z-index: 100;
}

.ellipse {
  width: 3000px;
  height: 250px;
  position: absolute;
  background: #1241C566; /* Couleur RGBA */
  filter: blur(150px); /* Applique du flou */
  border-radius: 50%; /* Forme d'ellipse */
  z-index: 0;
}

/* Positionnement initial */
.ellipse-center {
  top: 50%; /* Centrage vertical */
  left: 50%; /* Centrage horizontal */
  transform: translate(-30%, -50%) rotate(235.37deg); /* Centrer et orienter */
}

.ellipse-left {
  top: 50%; /* Positionner en haut à gauche */
  left: -500px; /* Décaler vers la gauche */
  transform: translate(-20%, -10%) rotate(235.37deg); /* Orientation */
}



.title {
  font-size: 54.6px;
  font-weight: 700;
}

.blue-title {
  background: radial-gradient(circle at 60% 100%, #043BCB, #88B3FD); /* Définir un dégradé radial */
  -webkit-background-clip: text; /* Affiche le gradient uniquement sur le texte */
  -webkit-text-fill-color: transparent; /* Rend le fond transparent pour ne voir que le gradient */
}

.offer-button {
  position: relative; /* Nécessaire pour que le pseudo-élément se place correctement */
  padding: 8.25px 35.41px;
  font-size: 14.66px;
  font-weight: 400;
  border: solid 2px #97BAFF66;
  border-radius: 54px;
  background: linear-gradient(
    to right, 
    rgb(136, 179, 253), /* Couleur claire à gauche */
    rgb(79, 129, 255),  /* Couleur foncée au centre */
    rgb(136, 179, 253), 
    rgb(136, 179, 253)  /* Couleur claire à droite */
  );
  -webkit-background-clip: text; 
  -webkit-text-fill-color: transparent;
  z-index: 1; /* S'assurer que le texte est au-dessus */
  overflow: hidden; /* Masque tout dépassement du pseudo-élément */
}

.offer-button::before {
  content: '';
  position: absolute;
  top: 50%; 
  left: 50%;
  width: 150px; /* Largeur du cercle */
  height: 150px; /* Hauteur du cercle */
  background: linear-gradient(
    to bottom, 
    rgb(39, 118, 255), /* Plus clair en haut */
    rgb(2, 13, 40) /* Plus foncé en bas */
  );
  filter: blur(90px); /* Applique un flou au gradient */
  transform: translate(-50%, -50%); /* Centre le cercle derrière le bouton */
  z-index: -1; /* Place le gradient derrière le texte */
  border-radius: 50%;
}





















/* Résolution 1920x1080 */
@media screen and (max-width: 1920px) {
  .ellipse {
    width: 2245px;
    height: 191px;
    filter: blur(100px);
  }
}

/* Résolution 1440x1024 */
@media screen and (max-width: 1440px) {
  .ellipse {
    width: 1800px;
    height: 160px;
    filter: blur(200px);
  }
  .ellipse-left {
    left: -400px; /* Ajuste le positionnement */
  }
}

/* Résolution 720x480 */
@media screen and (max-width: 720px) {
  .ellipse {
    width: 1000px;
    height: 120px;
    filter: blur(150px);
  }
  .ellipse-center {
    transform: translate(-40%, -60%) rotate(235.37deg);
  }
  .ellipse-left {
    left: -200px;
    top: 40%;
  }
}

/* Résolution 1787x1140 */
@media screen and (max-width: 1787px) {
  .ellipse {
    width: 1140px;
    height: 90px;
    filter: blur(80px);
  }
  .ellipse-center {
    top: 50%;
    left: 50%;
    transform: translate(-40%, -60%) rotate(235.37deg);
  }
  .ellipse-left {
    left: -200px;
    top: 40%;
  }
}

@media screen and (min-width: 1310px) {
  .ellipse {
    width: 2000px;
    height: 200px;
    filter: blur(130px);
  }
  .ellipse-center {
    top: 50%;
    left: 50%;
    transform: translate(-30%, -60%) rotate(235.37deg);
  }
  .ellipse-left {
    left: -200px;
    top: 40%;
    transform: translate(-30%, -60%) rotate(235.37deg);
  }
}

</style>