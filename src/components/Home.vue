<script setup>
import Projects from "@/components/Projects.vue";
import Header from "@/components/Header.vue";
import Presentation from "@/components/Presentation.vue";
import Footer from "@/components/Footer.vue";

import gameOfLifeImage from "@/assets/projectScreens/gameOfLife.png"
import EPRImage from "@/assets/projectScreens/EPR.jpg"
import SentinelleImage from "@/assets/projectScreens/sentinelle.png"
import EnglishVoteImage from "@/assets/projectScreens/englishVote.png"
import StationMeteoImage from "@/assets/projectScreens/stationMeteo.jpg"

import ParticleSection from "@/components/ParticleSection.vue";


const projectList= [
  {
    name: "EPR de Flamanville",
    image : EPRImage,
    description: "Stage de 13 semaines réalisé dans le CNPE de Flamanville 3. Le stage consistait dans l'intégration d'une équipe de développement chargée de la création d'outils pour la section contrôle commande. Les technologies de ces outils sont : Angular, Python et Qt.",
    technologies: ["angular", "python", "graphql", "postgresql", "qt"]
  },
  {
    link: "https://github.com/awell00/game_of_life",
    name: "Jeu de la vie",
    image : gameOfLifeImage,
    description: "Ce projet consiste en l’implémentation en C++ du Game of Life de John Conway, un automate cellulaire simulant l’évolution d’une population sur une grille au fil d’itérations. Le programme dispose d'un mode graphique (SFML) et d'un mode CLI. L’architecture repose sur les principes SOLID. Des extensions comme la grille torique, les cellules obstacles ou l’ajout de motifs dynamiques enrichissent la simulation et offrent une grande flexibilité d’expérimentation.",
    technologies: ["cplusplus", "solid", "uml"]
  },
  {
    link: "https://github.com/RobinWoods/3W",
    name: "Station Météo",
    image : StationMeteoImage,
    description: "Ce projet d'école consistait en la création d'une station météo. Basée sur un Arduino Uno, elle intègre divers capteurs (température, humidité, GPS, luminosité, pression atmosphérique) et enregistre les données sur carte SD. Le tout est codé en C avec une attention apportée sur l'optimisation de place pour intégrer toutes les fonctionnalitées.",
    technologies: ["c", "arduino"]
  },
  {
    link: "https://sentinelle.derenty.net/",
    name: "Sentinelle",
    image : SentinelleImage,
    description: "Un site internet en HTML / CSS / JS crée dans le cadre d'un projet d'école. Le but était de créer une application reliée à une base de données, permettant de suivre les émissions de gaz en France. La base de données étant une BDD MySQL, j'ai créer une API en nodeJS afin de pouvoir communiquer avec elle.",
    technologies: ["html5", "css", "javascript", "nodedotjs", "mysql"]
  },
  {
    link: "https://englishvote.derenty.net",
    name: "English Vote",
    image : EnglishVoteImage,
    description: "Un site web en VueJS qui permet de voter pour une video et un acteur, tout ce cas dans le cadre d'un projet scolaire. La partie Front-End à été dévellopée en VueJS, la backend, en AdonisJS.",
    technologies: ["vuedotjs", "adonisjs", "mysql"]
  }
]

</script>

<template>
  <Header/>
  <Presentation/>
  <ParticleSection>
    <!--<Skills :skills-group="skills"/>-->
    <Projects :projects-list="projectList"/>
  </ParticleSection>
  <Footer/>
</template>

<style scoped>
</style>