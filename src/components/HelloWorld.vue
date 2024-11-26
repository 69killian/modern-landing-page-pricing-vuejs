<template>
  <div :class="{'fade-in-loaded': isLoaded}">
    <div class="ellipse ellipse-center"></div>
    <div class="ellipse ellipse-left"></div>

    <div class="center-content">
      <div class="offer-button">
        Nos offres
      </div>

      <div class="title">Des prix en accord avec <span class="blue-title"><br/>notre vision</span></div>

      <div class="buttons">
          <div :class="{'button-clicked': isMonthly, 'button-unclicked': !isMonthly}" @click="togglePayment('monthly')">Paiement Mensuel</div>
          <div :class="{'button-clicked': !isMonthly, 'button-unclicked': isMonthly}" @click="togglePayment('annually')">Paiement Annuel (-20%)</div>
      </div>

      <div class="flex-row-cards">
        <div class="card1">
          <img src="../assets/icon1.png" alt="icon1">
          <div class="card-title">Essentiel</div>
          <div class="price">
            {{ isMonthly ? '$' + price1 : '$' + price4  }}
            <span class="month" v-if="isMonthly">/month</span>
            <span class="month" v-else>/year</span>
          </div>
          <div class="bottom-line"></div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +2500 vues/mois</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +60 clics sur votre site</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +15 appels/mois</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +15 demandes d'itinéraires</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> Plus de visibilité sur Google</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> Réponse aux avis Google inclus</div>
          <button class="subscribe-button">je m'abonne</button>
        </div>

        <div class="card2">
          <img src="../assets/icon2.png" alt="icon2">
          <div class="title-and-offer">
            <div class="card-title">Ultime</div>
            <div class="best-offer-button">Best Offer</div>
          </div>
          
          <div class="price">
            {{ isMonthly ? '$' + price2 : '$' + price5 }}
            <span class="month" v-if="isMonthly">/month</span>
            <span class="month" v-else>/year</span>
          </div>
          <div class="bottom-line"></div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +6500 vues/mois</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +200 clics sur votre site</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +40 appels/mois</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +40 demandes d'itinéraires</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> Plus de visibilité sur Google</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> Réponse aux avis Google inclus</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> 1 shooting</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> QR code personnalisé</div>
          <button class="subscribe-button">je m'abonne</button>
        </div>

        <div class="card3">
          <img src="../assets/icon1.png" alt="icon1">
          <div class="card-title">Premium</div>
          <div class="price">
            {{ isMonthly ? '$' + price3 : '$' + price6 }}
            <span class="month" v-if="isMonthly">/month</span>
            <span class="month" v-else>/year</span>
          </div>
          <div class="bottom-line"></div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +11 000 vues/mois</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +500 clics sur votre site</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +80 appels/mois</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> +80 demandes d'itinéraires</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> Plus de visibilité sur Google</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> Réponse aux avis Google inclus</div>
          <div class="card-text"><img src="../assets/Vector.png" alt=""> 1 shooting</div>
          <button class="subscribe-button">je m'abonne</button>
        </div>
      </div>
    </div>
  </div>
</template>



<script>
export default {
  data() {
    return {
      price1: 179,
      price2: 439,
      price3: 319,
      price4: Math.round((179 * 12) * 0.80), 
      price5: Math.round((439 * 12) * 0.80), 
      price6: Math.round((319 * 12) * 0.80), 
      isMonthly: true,
      isLoaded: false, // Ajoute un état pour savoir si le DOM est prêt
    };
  },
  mounted() {
    // Une fois que le composant est monté, applique la classe fade-in-loaded
    document.addEventListener('DOMContentLoaded', () => {
      this.isLoaded = true;
    });
  },
  methods: {
    togglePayment(paymentType) {
      if (paymentType === 'monthly') {
        this.isMonthly = true;
      } else if (paymentType === 'annually') {
        this.isMonthly = false;
      }
    }
  }
};
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
  overflow: hidden;
}



@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.fade-in {
  animation: fadeIn 1s ease-in-out;
}

.fade-in-loaded .ellipse,
.fade-in-loaded .center-content,
.fade-in-loaded .flex-row-cards {
  opacity: 1;
  animation: fadeIn 1s ease-in-out;
}

.center-content {
  display: flex; /* Active Flexbox */
  flex-direction: column; /* Aligne les éléments verticalement */
  align-items: center; /* Centre horizontalement */
  justify-content: center; /* Centre verticalement */
  text-align: center; /* Centre le texte */
  min-height: 100vh; /* Prend toute la hauteur de la page */
  gap: 20px; /* Espace entre les éléments */
  opacity: 0;
}

.flex-row-cards {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  gap: 30px;
  opacity: 0;
  padding: 100px;
}

.card1, .card2, .card3 {
  z-index: 100;
  height: auto; /* Ajuste la hauteur en fonction du contenu */
  width: auto;
  display: flex;
  align-items: flex-start; /* Aligne le contenu au début */
  flex-direction: column;
}

.card1, .card3 {
  padding: 50.81px;
  gap: 12.33px;
  background: radial-gradient(circle at 50% 100%, #051640, #1e6ffbe9 120%);
  border-radius: 20.03px;
  border: solid 1px #97baffb9;
}

.card2 {
  padding: 50.81px;
  gap: 12.33px;
  background-color: #A3D7FD;
  border-radius: 20.03px;
  border: solid 1px #97baffb9;
  background-image: url('../assets/Pattern.png'); /* Utilise l'image comme fond */
  background-size: cover; /* Couvre entièrement la carte */
  background-position: center; /* Centre l'image dans la carte */
  background-repeat: no-repeat; /* Empêche l'image de se répéter */
  box-shadow: 0px 0px 80px 1px #ffffff2d; /* Ombre interne blanche au survol */
}

.best-offer-button {
  background-color: #a3d7fd3a;
  border: 1px solid white;
  padding: 5px 10px;
  border-radius: 5px;
  font-size: 14px;
}

.title-and-offer {
  display: flex;
  background: none;
  align-items: center;
  gap: 15px;
}






.card1 .bottom-line, .card2 .bottom-line, .card3 .bottom-line {
  width: 100%; 
  height: 2px; /* Épaisseur de la ligne */
  background: linear-gradient(
  to right,
  rgba(151, 186, 255, 0) 0%, /* Transparent à gauche */
  rgba(151, 186, 255, 0.73) 50%, /* Couleur principale au centre */
  rgba(151, 186, 255, 0) 100% /* Transparent à droite */
);

  margin: 20px auto; /* Centre la ligne horizontalement et ajoute un espacement vertical */
  display: block; 
  border-radius: 1px; /* Ajoute un léger arrondi pour un effet moderne */
}


.card-text {
  font-size: 18.49px;
  background: none;
}

.card1 img, .card2 img, .card3 img {
  background: none;
}

.card1 .subscribe-button, .card3 .subscribe-button {
  position: relative;
  display: block;
  width: 100%;
  margin: 0 auto;
  padding: 10.25px 25.41px;
  border: solid 1px #FFFFFF66;
  border-radius: 9.17px;
  background: none; /* Fond transparent initial */
  color: white;
  cursor: pointer;
  text-align: center;
  transition: border-color 0.2s ease; /* Animation de la bordure */
  z-index: 1;
  overflow: hidden; /* Masque le contenu débordant */
}

.card1 .subscribe-button::before, .card3 .subscribe-button::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle at 50% 100%, #05164085, #1e6ffbe9 80%);
  z-index: -1; /* Le pseudo-élément est derrière le contenu */
  transition: opacity 0.2s ease; /* Transition sur l'opacité */
  opacity: 0; /* Initialement invisible */
}

.card1 .subscribe-button:hover::before, .card3 .subscribe-button:hover::before {
  opacity: 1; /* Rend le dégradé visible */
}

.card1 .subscribe-button:hover, .card3 .subscribe-button:hover {
  border-color: #ffffff9d; /* Change la bordure au survol */
}

.card2 .subscribe-button {
  position: relative;
  display: block;
  width: 100%;
  margin: 0 auto;
  padding: 10.25px 25.41px;
  border: solid 1px #FFFFFF66;
  border-radius: 9.17px;
  background: radial-gradient(circle at 50% 100%, #051640, #1e6ffbe9 120%);
  cursor: pointer;
  transition: box-shadow 0.2s ease; /* Transition fluide sur l'ombre interne */
}

.card2 .subscribe-button:hover {
  box-shadow: inset 0px 0px 10px 2px #1e6ffba3; /* Ombre interne blanche au survol */
}




.subscribe-button {
  font-size: 18.49px;
}


.card-title {
  font-size: 33.9px;
  background: none;
}

.price {
  font-size: 46.22px;
  background: none;
}

.month {
  font-size: 16px;
  background: none;
}

.ellipse {
  width: 3000px;
  height: 250px;
  position: absolute;
  background: #1241C566; /* Couleur RGBA */
  filter: blur(150px); /* Applique du flou */
  border-radius: 50%; /* Forme d'ellipse */
  z-index: 0;
  opacity: 0;
  
  /* Limiter la taille de l'ellipse pour qu'elle ne déborde pas */
  max-width: 100vw; /* Empêche l'ellipse de dépasser la largeur de la fenêtre */
  max-height: 100vh; /* Empêche l'ellipse de dépasser la hauteur de la fenêtre */
}

/* Positionnement initial */
.ellipse-center {
  top: 50%; /* Centrage vertical */
  left: 50%; /* Centrage horizontal */
  transform: translate(-30%, -50%) rotate(235.37deg); /* Centrer et orienter */
}

/* Positionnement à gauche */
.ellipse-left {
  top: 50%; /* Positionner en haut à gauche */
  left: -500px; /* Décaler vers la gauche */
  transform: translate(-20%, -10%) rotate(235.37deg); /* Orientation */
  /* Empêcher le débordement latéral */
  max-width: calc(100vw + 500px); /* Prendre en compte le décalage */
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
  border: solid 1px #97BAFF66;
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


.offer-button {
  position: relative; /* Nécessaire pour que le pseudo-élément se place correctement */
  padding: 10.25px 45.41px;
  font-size: 14.66px;
  font-weight: 400;
  border: solid 1px #97BAFF66;
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
  box-shadow: inset 0 0 10px 2px rgba(1, 33, 160, 0.115); /* Ombre interne blanche */
}

.button-clicked {
  border: solid 1px #FFFFFF66;
  padding: 10.25px 45.41px;
  border-radius: 9.17px;
  background: radial-gradient(circle at 50% 90%, #0A308B, #1E6EFB);
  box-shadow: inset 2px 2px 10px 2px #1E6EFB;
  cursor: pointer;
  transition: 0.2s;
}

.button-clicked:hover {
  background: radial-gradient(circle at 50% 90%, #0A308B, #1E6EFB);
  box-shadow: inset 2px 2px 10px 2px #1e6ffb00;
}

.button-unclicked {
  border: solid 1px #FFFFFF66;
  background: radial-gradient(circle at 50% 90%, #0a318b00, #1e6ffb00);
  padding: 10.25px 25.41px;
  border-radius: 9.17px;
  box-shadow: inset 0 0 10px 2px rgba(1, 33, 160, 0.347);
  cursor: pointer;
  transition: 0.2s;
  z-index: 10000;
}

.button-unclicked:hover {
  border: solid 1px #ffffff92;
  color: white;
}

.buttons {
  display: flex;
  gap: 15px;
  margin-bottom: -50px;
  z-index: 10000000;
  background: none;
}





















/* Résolution 1920x1080 */
@media screen and (max-width: 1920px) {

  .center-content {
    padding: 50px;
  }
  .ellipse {
    width: 2245px;
    height: 191px;
    filter: blur(100px);
  }
}

@media screen and (max-width: 1473px) and (min-height: 694px) {
  * {
    overflow: scroll;
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

  * {
    overflow: auto;
  }
  .card1, .card3 {
    width: 80% !important; /* Les cartes prennent toute la largeur */
    font-size: 12px; /* Réduire encore la taille du texte */
    padding: 20px; /* Réduire l'espacement interne des cartes */
  }


  .button-clicked {
    font-size: 12px;
  }

  .button-unclicked {
    font-size: 12px;
  }

  .card2 {
    width: 100% !important;
  }
  .price {
    font-size: 30px; /* Réduire la taille du prix */
  }
  .month {
    font-size: 12px; /* Ajuster la taille du texte mois */
  }
  .flex-row-cards {
    flex-direction: column; /* Mettre les cartes en colonne */
    align-items: center;
    gap: 20px; /* Espacement entre les cartes */
  }
  .title {
    font-size: 24px; /* Réduire la taille du titre */
  }
  .blue-title {
    font-size: 20px; /* Réduire la taille du texte avec gradient */
  }
  .offer-button {
    font-size: 12px; /* Réduire la taille du bouton */
    margin-top: 20px;
  }
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