<script setup>
import Project from "@/components/Project.vue";

defineProps({
  projectsList : Array
})
</script>

<template>
  <div>
    <h1>Mes Projets</h1>
    <div class="projects">
      <Project v-for="project in projectsList" :project="project"/>
    </div>
  </div>

</template>

<style scoped>

div{
  text-align: center;
  margin-top: 5rem;
}



.projects{
  margin-top:0;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  align-content: center;
  flex-wrap: wrap;
  margin-inline: 2rem;
}

</style>