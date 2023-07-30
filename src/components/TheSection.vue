<template>
  <section>
    <div class="main-hero">
      <h1>{{ title }}</h1>
      <div class="button-container">
        <TheButton>{{ firstButton }}</TheButton>
        <TheButton variant="white">{{ secondButton }}</TheButton>
      </div>
    </div>
    <div class="grid-container">
      <div class="card-block" v-for="bloco in blocos" :key="bloco.id">
        <img v-if="imgMap[bloco.id]" :src="imgMap[bloco.id]" alt="Blocos Image" />
        <div class="loading" v-else>
            LOADING...
        </div>
        <h3>{{ bloco.name }}</h3>
        <p>{{ bloco.description }}</p>
        <p>{{ bloco.location }}</p>
      </div>
    </div>
  </section>
</template>

<script>
import blocos from "../data/blocos";
import TheButton from "./atoms/TheButton.vue";

export default {
    name: "TheSection",
    data() {
        return {
            blocos: blocos,
            title: "Blocos recomendados",
            firstButton: "Lista",
            secondButton: "Mapa",
            imgMap: {},
        };
    },
    mounted() {
        this.blocos.forEach((bloco) => {
            import(`../assets/${bloco.image}.png`).then((image) => {
                this.imgMap[bloco.id] = image.default;
            });
        });
        console.log(this.imgMap);
    },
    components: { TheButton }
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
  display: flex;
  gap: 8px;
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

.loading {
    height: 153px;
    background-color: grey;
    border-radius: 8px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    font-weight: bold;
}
</style>
