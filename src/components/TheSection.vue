<template>
  <section>
    <div class="main-hero">
      <h1>{{ title }}</h1>
      <div class="button-container">
        <TheButton>{{ firstButton }}</TheButton>
        <TheButton variant="white">{{ secondButton }}</TheButton>
      </div>
    </div>
    <the-cards></the-cards>
  </section>
</template>

<script>
import TheCards from "../components/TheCards.vue";
import TheButton from "../components/atoms/TheButton.vue";
export default {
  name: "TheSection",
  data() {
    return {
      title: "Blocos recomendados",
      firstButton: "Lista",
      secondButton: "Mapa",
    };
  },
  components: { TheButton, TheCards },
};
</script>

<style lang="scss">
section {
  margin: 10rem 11.2rem 10rem;
  max-width: 121.6rem;
  max-height: 112.1rem;
}
.main-hero {
  display: flex;
  align-items: center;
  text-transform: uppercase;
  justify-content: space-between;
}
.button-container {
  padding: 0.8rem;
  display: flex;
  gap: 0.8rem;
}

.loading {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 15.3rem;
  background-color: $gray1;
  border-radius: 0.8rem;
  color: $white;
  font-weight: bold;
}
</style>
