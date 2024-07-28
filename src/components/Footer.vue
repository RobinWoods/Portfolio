<script setup>

import SocialsWidgets from "@/components/SocialsWidgets.vue";
const socialsNames = ["linkedin", "github"];
</script>

<template>
<div>
  <div class="socials">
    <SocialsWidgets v-for="social in socialsNames" :key="social" :social="social"/>
  </div>
  <p>HandCrafted by Me and Inspiring by <a href="https://mattfarley.ca/" target="_blank">Matt Farley</a></p>

</div>
</template>

<style scoped>

div{
  background-color: var(--custom-blue-color);
  height: 15rem;
  margin-top: 3rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: white;
}

.socials{
  flex-direction: row;
  justify-content: space-between;
  max-height: fit-content;
  gap: 1rem;
}


a{
  text-decoration: none;
  color: white;
}

p{
  padding: 0.5rem;
  text-align: center;
}

</style>