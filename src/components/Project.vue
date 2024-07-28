<script setup>
defineProps(['project'])
let width = null
if (typeof window !== 'undefined') {
  width = window.screen.width;
}
</script>

<template>
  <div>
    <h2><a :href="project.link" target="_blank">{{project.name}}</a></h2>
    <p>{{project.description}}</p>
    <iframe v-if="width >= 500" :src="project.link" class="projectIntegration" :title="project.name"></iframe>
  </div>
</template>

<style scoped>

div{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-content: center;
  padding:0;
  padding-inline: 1.5rem;
  border: solid;
  border-radius: 1.2rem;
  width: 100%;
  min-height: fit-content;
  background-color: var(--custom-blue-color);
  color: white;
}

.projectIntegration{
  width: 100%;
  height: 20rem;
  margin: 2rem;
  border-radius: 2rem;
}

a{
  color: white;
  text-decoration: none;
}

</style>