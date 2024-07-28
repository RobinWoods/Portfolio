<script setup>

</script>

<template>
  <div>
    <img src="@/assets/logo.png" alt="logo" class="logo"/>
    <button class="contactButton">Contact-Me</button>
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