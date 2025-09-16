<script setup xmlns="http://www.w3.org/1999/html">

</script>

<template>
  <div>
    <a href="/public/pdf/CV_RDerenty.pdf" target="_blank" ><img src="@/assets/robinHood.png" alt="Robin Hood" class="robinHood"/></a>
    <p>⬆️ Télécharger mon CV ⬆️</p>
    <h1>Robin Derenty</h1>
    <h2>Étudiant Ingénieur Informatique</h2>
    <div class="presentationBlock">
      <p>Passionné d’informatique depuis l’enfance, ma rigueur et mon envie de toujours apprendre plus m’ont conduit à entreprendre des études d’ingénieur dans ce domaine.</p>
      <p>Mon parcours académique et mes expériences professionnelles témoignent de ma capacité à mener des projets innovants et à m’adapter rapidement aux nouvelles technologies. Je suis actuellement étudiant en classe préparatoire en informatique, prêt à relever de nouveaux défis et à contribuer à des projets ambitieux.</p>
    </div>
  </div>

</template>

<style scoped>
div{
  justify-content: center;
  text-align: center;
}

.presentationBlock{
  background-color: var(--custom-blue-color);
  color: white;
  font-size: large;
  align-content: center;
  padding: 1rem;
  padding-inline: 5rem;
  vertical-align: baseline;
  min-height: 20rem;

}

img{
  border-radius: 50%;
  transition-duration: 0.2s;
  animation: float 4s ease-in-out infinite;
  cursor: pointer;
}

@keyframes float {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-0.5rem);
  }
  100% {
    transform: translateY(0);
  }
}

img:hover{
  scale: 1.05;
}

</style>