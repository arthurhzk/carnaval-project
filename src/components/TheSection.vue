<template>
  <section>
    <div class="main-hero">
      <h1>{{ title }}</h1>
      <div class="button-container">
        <button id="purple-button">{{ firstButton }}</button>
        <button id="white-button">{{ secondButton }}</button>
      </div>
    </div>
    <div class="grid-container">
      <div class="card-block" v-for="bloco in blocos" :key="bloco.id">
        <img :src="`./assets/${bloco.image}`" alt="Blocos Image" />
        <h3>{{ bloco.name }}</h3>
        <p>{{ bloco.description }}</p>
        <p>{{ bloco.location }}</p>
      </div>
    </div>
  </section>
</template>

<script>
import blocos from "../data/blocos";
export default {
  name: "TheSection",
  data() {
    return {
      blocos: blocos,
      title: "Blocos recomendados",
      firstButton: "Lista",
      secondButton: "Mapa",
    };
  },
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
  padding: 8px;
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
#purple-button {
  background-color: $purple;
  color: $white;
}
#white-button {
  background-color: $white;
  color: $purple;
}
#purple-button:hover {
  opacity: 0.8;
}
#white-button:hover {
  visibility: 0.8;
  background-color: rgba(0, 0, 0, 0.1);
}
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  align-items: center;
  justify-content: center;
}
.card-block {
  margin-top: 41.5px;
  gap: 32px;
  width: 384px;
  height: 323px;
  padding: 16px;
  border-radius: 10px;
  border: 1px solid #eaeaea;
  background: #fff;
}

img {
  width: 384px;
  height: 153px;
}
</style>
