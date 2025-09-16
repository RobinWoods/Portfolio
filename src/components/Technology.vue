<script setup>

import technology from "@/components/Technology.vue";
import {computed} from "vue";

const props = defineProps({
  technology: String
});

const cdn_link  = computed(() => {
  return `https://cdn.simpleicons.org/${props.technology}/ffffff`;
})
</script>

<template>
  <img height="32" width="32" :src="cdn_link" :alt="technology" class="technology-icon"/>
</template>

<style scoped>

</style>