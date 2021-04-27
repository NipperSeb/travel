<template>
  <div class="row">
    <div class="sideLeft">
      <p>
        <img src="@/assets/seb3.jpg" id="photo" alt="Seb" title="Seb" />
      </p>
      <div class="vertical-menu">
        <a href="#about">
          <span class="rect"></span>
          <span class="circle"></span>
          A propos</a
        >
        <a href="#competence">
          <span class="rect"></span>
          <span class="circle"></span>
          Mes compétences</a
        >
        <a href="#formation">
          <span class="rect"></span>
          <span class="circle"></span>
          Mes formations</a
        >
        <a href="#experience">
          <span class="rect"></span>
          <span class="circle"></span>
          Mes expériences</a
        >
      </div>
    </div>
    <div class="sideRight">
      <section id="about" v-scrollanimation>
        <h1><br />Sébastien <b class="peer"> Pincepoche</b></h1>
        <div class="contact">
          <p>
            4 RUELLE DES ANGLAIS - 35 300 FOUGERES - 06.71.73.38.54 -
            <b class="peer">sebastien.pincepoche@wanadoo.fr</b><br />Né le
            02/04/1976
          </p>
        </div>
        <blockquote>
          <p>
            <em><br />"Rien n'est permanent sauf le changement" Héraclite</em>
          </p>
        </blockquote>
        <div class="presentation">
          <p>
            Je suis Chef De Rayon Charcuterie/Fromage à la Coupe depuis plus de
            12 ans. En 2015, j'ai obtenu via une VAE un Titre Professionnel MUM
            (équivalent du BTS MUC), puis un DUT GEA option Gestion et
            Management en 2017 et depuis, je consacre mon temps libre à
            l'apprentissage du digital (CSS, HTML, Javascript et PHP). Mon idéal
            serait de pouvoir faire évoluer ces métiers traditionnels à l'aide
            du digital en m'appuyant sur mon expérience et mes formations
            obtenues.
          </p>
        </div>
      </section>

      <section id="competence" class="content-section" v-scrollanimation>
        <h2>Mes compétences</h2>
        <ul class="comp">
          <li>Encadrer une équipe de vente</li>
          <li>Etablir une organisation de travail</li>
          <li>Bonne aptitude à travailler en équipe</li>
          <li>Capacité d'adaptation</li>
          <li>Sens de l'initiative</li>
          <li>
            Pragmatique
          </li>
          <li>Bon niveau d'anglais</li>
        </ul>
      </section>

      <section id="formation" class="content-section" v-scrollanimation>
        <h2>Mes formations</h2>
        <ul>
          <li>
            <strong>2017 : DUT GEA option gestion et management</strong
            ><br />Université de Rennes
          </li>
          <li>
            <strong
              >2015 : Titre Professionnel Manager d'Univers Marchand (niveau
              III)</strong
            ><br />AFPA Rennes
          </li>
          <li>
            <strong>1996 : Baccalauréat Technologique Hôtelier</strong
            ><br />Lycée hôtelier Dinard
          </li>
        </ul>
      </section>

      <section id="experience" class="content-section" v-scrollanimation>
        <h2>Mes expériences</h2>
        <ul>
          <li>
            <strong
              >De 2006 à aujourd'hui : Chef de Rayon. Intermarché
              Liffré.</strong
            ><br />
            Je suis reponsable du compte d'exploitation du rayon et du
            management d'une équipe de 3 personnes.<br />En charge du suivi des
            différents objectifs (marges, chiffres d'affaires) et de la relation
            avec les fournisseurs. Analyse de la rentabilité des produits.
          </li>
          <li>
            <strong
              >Du 24/04/2017 AU 30/06/2017 : Stage Assistant de Gestion.
              SystemGie Cesson-Sévigné.</strong
            ><br />
            Mon stage consistait à faire du Sourcing, de l'enregistrement de
            factures et la réalisation d'un rapport de stage sur la mise en
            oeuvre d'une "Démarche Qualité ISO 9001" au sein de ce service.
          </li>
          <li>
            <strong
              >De 2002 à 2006 : Adjoint-Manager Produits Frais. Hyper U
              Vitré</strong
            ><br />
            J'étais en charge de seconder le Manager, gérer les stocks et
            assurer la présentation marchande des produits.
          </li>
          <li>
            <strong
              >De 2000 à 2002 : Assistant Commercial. Casino Fougères</strong
            ><br />Mise en place d'animation commerciale, enregistrement des
            recettes et management d'une équipe de 8 personnes.
          </li>
          <li>
            <strong>De 1996 à 2000 : Cuisinier en France et Angleterre.</strong>
          </li>
        </ul>
      </section>
    </div>
  </div>
</template>

<style scoped>
* {
  text-align: left;
}

.content-section {
  padding-top: 10.5%;
  border-bottom: solid;
}

.row {
  box-sizing: border-box;
  margin: 0;
  font-family: "Times New Roman", Times, serif;
  font-size: 1.3em;
  background-color: rgb(245, 234, 234);
}

.sideLeft {
  background: #baf3e8;
  padding: 20px;
  position: fixed;
  top: 10.5%;
  z-index: 10;
  height: 100%;
}

.sideRight {
  position: relative;
  padding-left: 250px;
}

.vertical-menu p,
a {
  color: black;
  display: block;
  text-decoration: none;
  padding: 10px;
}

.vertical-menu a:hover,
.vertical-menu .active-section {
  color: rgb(235, 157, 69);
}

.vertical-menu a:hover span,
.vertical-menu .active-section span {
  background-color: rgb(235, 157, 69);
}

.vertical-menu .active-section .rect {
  width: 40px;
}

h2 {
  font-size: 2.5em;
}

b,
h2 {
  color: rgb(235, 157, 69);
}

h1 {
  font-size: 3.5em;
}

img {
  width: 140px;
  height: 140px;
  margin-top: 15px;
  border-radius: 12px;
  border-style: solid;
  border-color: black;
  padding: 10px;
}

.contact {
  font-size: 1.5em;
  word-wrap: break-word;
}

li {
  line-height: 2;
}

.before-enter {
  opacity: 0;
  transform: translaleY(100px);
  transition: all 3s ease-out;
}

.enter {
  opacity: 1;
  transform: translaleY(0px);
}

span {
  display: inline-block;
  position: relative;
}

.circle {
  height: 10px;
  width: 10px;
  left: -10px;
  border-radius: 50%;
  background-color: #272727;
}

@media only screen and (max-width: 500px) {
  .sideLeft {
    display: none;
  }
  .sideRight {
    padding-left: 10px;
    width: 100%;
  }
  h1 {
    font-size: 2.5em;
  }
  .contact {
    font-size: 1.5em;
  }
  .row {
    font-size: 1em;
  }
}
</style>
