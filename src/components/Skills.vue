<script setup>
import SkillsBlock from "@/components/SkillsBlock.vue";

defineProps({
  skillsGroup: Object,
})
</script>

<template>
<div class="skills">
    <h1>Skills</h1>
    <div class="skillGroups">
      <div class="skillsBlock">
        <SkillsBlock v-for="skillsGroup in skillsGroup" :skillsGroup="skillsGroup.group" :skills="skillsGroup.skills"/>
      </div>
    </div>

  </div>
<div/>
</template>

<style scoped>

.skills{
  text-align: center;
}
.skillsBlock{
  display: flex;
  flex-direction: row;
  border: solid;
  box-shadow: 0.2rem 0.2rem 0.2rem #000000;
  border-radius: 1.2rem;
  width: fit-content;
}

.skillGroups{
  display: flex;
  flex-direction: row;
  justify-content: center;
}

</style>