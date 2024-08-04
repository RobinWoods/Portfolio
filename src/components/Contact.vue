<script setup>
import { ref } from 'vue';


const name = ref('');
const email = ref('');
const message = ref('');


let props = defineProps(['isVisible']);

const emit = defineEmits(['close']);

function close(){
  emit('close');
}

async function sendMail(){
  fetch(import.meta.env.VITE_APP_MAIL_SERVER_URL, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({
      name: name.value,
      email: email.value,
      message: message.value
    })
  })
  .then(response => response.json())
  .then(data => {
    console.log('Success:', data);
  })
  .catch(error => {
    console.error('Error:', error);
  });
  close();
}

</script>

<template>
  <div class="greyDiv" v-if="props.isVisible">
    <div class="enclosureDiv">
      <div class="closeDiv">
        <img src="@/assets/crossIcon.png" alt="cross Icon" class="crossButton" @click="close">
      </div>
      <div  class="contactDiv">
        <h1>Contactez-Moi</h1>
        <label for="name">Votre Nom :</label>
        <input type="text" placeholder="Nom" v-model="name" name="name"/>
        <label for="email">Votre Email :</label>
        <input type="email" placeholder="Email" v-model="email" name="email"/>
        <label for="message">Votre Message :</label>
        <textarea placeholder="Message" style="min-width: 100%; max-width: 100%; min-height: 3rem" v-model="message" name="message"></textarea>
        <button class="sendButton" @click="sendMail">Envoyer</button>
      </div>
    </div>
  </div>

</template>

<style scoped>

.closeDiv{
  display: flex;
  justify-content: flex-end;
  background-color: var(--custom-blue-color);
  border-radius: 1rem 1rem 0 0;
  min-width: 10rem;
  height: fit-content;
  z-index: 1001;
}

.greyDiv{
  position: fixed;
  display: flex;
  top: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.enclosureDiv{
  display: flex;
  flex-direction: column;
  z-index: 1001;
  max-width: 70%;
}


.contactDiv{
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 1rem;
  background-color: white;
  border-radius:  0 0 1rem 1rem;
  z-index: 1001;
}

.crossButton{
  height: 1rem;
  padding: 0.5rem;
  transition-duration: 0.2s;
}

.crossButton:hover{
  scale: 1.05;
}

.sendButton{
  border: solid 0.2rem var(--custom-blue-color); ;
  border-radius: 1.5rem;
  background-color: transparent;
  color: var(--custom-blue-color);
  min-height: 2.4rem;
  min-width: 4rem;
  transition-duration: 0.2s;
  align-self: flex-end;
}


.sendButton:hover{
  background-color: var(--custom-blue-color);
  color: white;
  scale: 1.05;
}

</style>