<script setup>
import Projects from "@/components/Projects.vue";
import Header from "@/components/Header.vue";
import Presentation from "@/components/Presentation.vue";
import Skills from "@/components/Skills.vue";
import Footer from "@/components/Footer.vue";

const skills = {
  dev: {
    group: "Dev",
    skills: ["Web3", "Java", "C", "Python"]
  },
  system: {
    group: "System",
    skills: ["Linux", "Apache", "Docker", "SQL"]
  },
  tools: {
    group: "Tools",
    skills: ["Git", "Méthode Agile", "Visual Studio", "Postman"]
  }
}

const projectList= [
  {
    link: "https://sentinelle.derenty.net/",
    name: "Sentinelle",
    description: "Un site internet en web3 crée dans le cadre d'un projet d'école. Le but était de créer une application reliée à une base de données, permettant de suivre les émissions de gaz en France. La base de données étant une BDD MySQL, j'ai créer une API en nodeJS afin de pouvoir communiquer avec elle."
  },
  {
    link: "https://englishvote.derenty.net",
    name: "English Vote",
    description: "Un site web en VueJS qui permet de voter pour une video et un acteur, tout ce cas dans le cadre d'un projet scolaire. La partie Front-End à été dévellopée en VueJS, la backend, en AdonisJS."
  }

]
</script>

<template>
  <Header/>
  <Presentation/>
  <Skills :skills-group="skills"/>
  <Projects :projects-list="projectList"/>
  <Footer/>
</template>

<style scoped>
</style>