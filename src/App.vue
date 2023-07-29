<script setup></script>

<template>
  <the-hero></the-hero>
  <the-section></the-section>
</template>

<script>
import TheHero from "./components/TheHero.vue";
import TheSection from "./components/TheSection.vue";
export default {
  components: {
    TheHero,
    TheSection,
  },
};
</script>
<style lang="scss" scoped></style>
