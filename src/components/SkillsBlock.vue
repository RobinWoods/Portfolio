<script setup>
defineProps({
  skillsGroup: String,
  skills: Array
})

function getImageURL(title){
  console.log(`@/assets/${title}.svg`)
  return `src/assets/${title}.svg`
}
</script>

<template>
  <div>
    <img :src="getImageURL(skillsGroup)" :alt="`${skillsGroup} Logo`" class="skillsLogo">
    <h2>{{skillsGroup}}</h2>
    <div class="skillsList">
      <ul v-for="skill in skills" style="color:var(--custom-blue-color);">{{skill}}</ul>
    </div>
  </div>
</template>

<style scoped>
div{
  text-align: center;
  align-content: center;
  justify-items: center;
  min-width: 7rem;
  padding: 1rem;
}

.skillsList{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  align-content: center;

  ul{
    margin-inline: 0;
    padding-inline: 0;
  }
}


.skillsLogo{
  width: 3rem;
  height: auto;
}

</style>