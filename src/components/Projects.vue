<script setup>
import Project from "@/components/Project.vue";
import projectsData from "@/data/projects.json"

function getImage(fileName) {
  return new URL(`../assets/projectScreens/${fileName}`, import.meta.url).href;

}

let projectsList = projectsData.map(project => ({
  ...project,
  image: getImage(project.image)
}))

projectsList = projectsList.sort((a, b) => a.index - b.index);

</script>

<template>
  <div>
    <h1>Mes Projets</h1>
    <div class="projects">
      <div class="project-item" v-for="project in projectsList" :key="project.index">
        <Project :project="project"/>
      </div>
    </div>
  </div>

</template>

<style scoped>

h1{
  color: black;
}

div{
  text-align: center;
  margin-top: 5rem;
}

.projects{
  margin-top: 0;
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin-inline: 2rem;
}

.project-item{
  display: flex;
}

.project-item:nth-child(odd){
  justify-content: flex-start;
}

.project-item:nth-child(even){
  justify-content: flex-end;
}

.project-item :deep(.project-container){
  margin: 0;
}

</style>