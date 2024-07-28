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
    skills: ["Git", "Agile Method", "Visual Studio", "Postman"]
  }
}

const projectList= [
  {
    link: "https://sentinelle.derenty.net/",
    name: "Sentinelle",
    description: "A fake web application made for a school project. The Website is connected to a SQL DataBase with an API."
  },
  {
    link: "https://englishvote.derenty.net",
    name: "English Vote",
    description: "A web application that allows you to vote on the best English word to describe a given image."
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