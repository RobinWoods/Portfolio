<script setup>
defineProps(['social'])
</script>

<template>
<div class="social">
  <a href="https://www.linkedin.com/in/robin-derenty-4575b8287/" target="_blank"> <img v-if="social === 'linkedin'" src="@/assets/socialsIcons/linkedinIcon.svg" :alt="social"/></a>
  <a href="https://github.com/RobinWoods" target="_blank"> <img v-if="social === 'github'" src="@/assets/socialsIcons/githubIcon.svg" :alt="social"/> </a>
</div>
</template>

<style scoped>
.social{
  height: 3.5rem;
  width: 3.5rem;
  border: white 0.15rem solid;
  border-radius: 50%;

  align-items: center;
  justify-content: center;
}

img{
  height: 2rem;
  width: auto;
}


</style>