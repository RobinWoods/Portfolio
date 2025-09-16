<script setup>
import {computed, ref} from 'vue';
import Technology from "@/components/Technology.vue";
import githubIcon from '@/assets/socialsIcons/githubIcon.svg';
import internetIcon from '@/assets/socialsIcons/internetIcon.svg';

const props = defineProps(['project'])
let width = null
if (typeof window !== 'undefined') {
  width = ref(window.screen.width);
}

const linkIcon = computed(() => {
  if (props.project && props.project.link) {
    if (props.project.link.startsWith('https://github.com/')) {
      return githubIcon;
    } else {
      return internetIcon;
    }
  }
  else {
    return null;
  }

})
</script>

<template>
  <div class="project-container">

    <div>
      <h2>{{props.project.name}}</h2>
      <a :href="props.project.link" target="_blank" v-if="props.project.link"><img class="linkLogo" :src="linkIcon" alt="Lien vers le projet"/></a>
      <p>{{props.project.description}}</p>
    </div>

    <div class="media-row">

      <div class="image-wrapper">
        <img v-if="props.project.image && width.valueOf() > 500" :src="props.project.image" :alt="props.project.name + ' image'" class="project-image"/>
      </div>

      <div class="technologies">
        <h3 class="technologies-title">Technologies utilisées</h3>
        <div class="technology-list">
          <Technology :technology="technology" v-for="technology in props.project.technologies" :key="technology"/>
        </div>
      </div>
    </div>

  </div>

</template>

<style scoped>

.project-container{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-content: center;
  padding:0;
  padding-inline: 1.5rem;
  padding-block: 1rem;
  border: solid;
  border-radius: 1.2rem;
  width: 100%;
  max-width: 40rem;
  min-height: fit-content;
  background-color: var(--custom-blue-color);
  color: white;
  margin: 0 auto;
}

.technologies{
  display: flex;
  flex-direction: column;
  max-width: 50%;
  justify-content: center;
  align-items: center;
  align-content: center;
  gap: 0.5rem;
}

.technology-list{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  align-content: center;
  gap: 1rem;
}

a{
  color: white;
  text-decoration: none;
}

.linkLogo{
  width: 2rem;
  height: 2rem;
}

.project-image{
  width: 100%;
  max-width: 28rem;
  height: 16rem;
  object-fit: cover;
  display: block;
  border-radius: 0.5rem;
}

/* White contour around Technology.vue icons */
.technologies :deep(.technology-icon) {
  border: 2px solid #ffffff;
  border-radius: 0.5rem;
  padding: 0.25rem;
  box-sizing: content-box;
}

/* Layout for image and technologies row */
.media-row{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  align-content: center;
  gap: 1.5rem; /* space between image and technologies */
  width: 100%;
}

.technologies-title{
  width: 100%;
  margin: 0 0 0.5rem 0;
  font-size: 1rem;
  font-weight: 600;
  text-align: center;
}


@media (max-width: 768px) {
  .media-row{
    flex-direction: column;
  }

  .project-container{
    min-width: 15rem;
  }
}
</style>
