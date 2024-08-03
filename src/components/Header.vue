<script setup>
import Contact from "@/components/Contact.vue";
import {ref} from "vue";

let isVisible = ref(false);

function showContact(){
  isVisible.value = true;
}

function hideContact() {
  isVisible.value = false;
}

</script>

<template>
  <div>
    <img src="@/assets/logo.png" alt="logo" class="logo"/>
    <button class="contactButton" @click="showContact" >Contact-Me</button>
    <Contact v-model:is-visible="isVisible" @close="hideContact" @show="console.log('Hello World')"/>
  </div>
</template>

<style scoped>
div{
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  padding: 1rem;
}

.logo{
  width: 100px;
  height: auto;
}

.contactButton{
  border: solid 0.2rem var(--custom-blue-color); ;
  border-radius: 1.5rem;
  background-color: transparent;
  color: var(--custom-blue-color);
  min-height: 2.8rem;
  min-width: 8rem;
  transition-duration: 0.2s;

}
.contactButton:hover{
  background-color: var(--custom-blue-color);
  color: white;
  scale: 1.05;
}

</style>