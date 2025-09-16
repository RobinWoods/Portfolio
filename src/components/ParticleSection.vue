<template>
  <div class="particles-section">
    <div id="particles-container"></div>
    <div class="section-content">
      <slot></slot>
    </div>
  </div>
</template>

<script setup>
import { onMounted, onBeforeUnmount } from "vue";

let resizeObserver;

onMounted(() => {
  if (!window.particlesJS) {
    console.error("particles.js non chargé !");
    return;
  }

  // Init particles
  particlesJS("particles-container", {
    particles: {
      number: { value: 50 },
      size: { value: 3 },
      move: { enable: true, speed: 5 },
      line_linked: {
        enable: true,
        distance: 150,
        color: "#2765af",
        opacity: 0.4,
        width: 2
      },
      color: { value: "#2765af" },
    },
    interactivity: {
      events: { onhover: { enable: true, mode: "repulse" } }
    }
  });

  // Ajuste automatiquement le canvas à la taille du conteneur
  const container = document.getElementById("particles-container");
  resizeObserver = new ResizeObserver(() => {
    container.querySelector("canvas").style.width = "100%";
    container.querySelector("canvas").style.height = "100%";
  });
  resizeObserver.observe(container);
});

onBeforeUnmount(() => {
  if (resizeObserver) resizeObserver.disconnect();
});
</script>

<style scoped>
.particles-section {
  position: relative;
  width: 100%;
  min-height: 300px;
  overflow: hidden;
}

#particles-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.section-content {
  position: relative;
  z-index: 1;
  color: white;
  padding: 2rem;
  text-align: center;
}
</style>
