<script setup>
import Projects from "@/components/Projects.vue";
import Header from "@/components/Header.vue";
import Presentation from "@/components/Presentation.vue";
import Footer from "@/components/Footer.vue";


import ParticleSection from "@/components/ParticleSection.vue";

</script>

<template>
  <Header/>
  <Presentation/>
  <ParticleSection>
    <!--<Skills :skills-group="skills"/>-->
    <Projects/>
  </ParticleSection>
  <Footer/>
</template>

<style scoped>
</style>