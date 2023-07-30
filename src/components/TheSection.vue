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
import TheButton from "./atoms/TheButton.vue";
import TheCards from "../components/TheCards.vue";
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
button {
  padding: 0.4rem 2.4rem;
  cursor: pointer;
  border: none;
  gap: 8px;
  border-radius: 0.5rem;
  text-align: center;
  font-size: 1.4rem;
  font-weight: 500;
  line-height: 2.4rem;
  text-transform: uppercase;
}

.loading {
  height: 15.3rem;
  background-color: grey;
  border-radius: 0.8rem;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  font-weight: bold;
}
</style>
