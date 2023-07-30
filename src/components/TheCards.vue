<template>
  <div class="grid-container">
    <div class="card-block" v-for="bloco in blocos" :key="bloco.id">
      <div class="information-container">
        <img
          v-if="imgMap[bloco.id]"
          :src="imgMap[bloco.id]"
          @click="searchBlockOnGoogle(bloco)"
          alt="Blocos Image"
        />
        <div class="loading" v-else>{{ loader }}</div>
        <h3>{{ bloco.name }}</h3>
        <p>{{ bloco.description }}</p>
        <p>{{ bloco.location }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import blocos from "../data/blocos";

export default {
  name: "TheCards",
  data() {
    return {
      blocos: blocos,
      imgMap: {},
      loader: "LOADING...",
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
  methods: {
    searchBlockOnGoogle(bloco) {
      if (bloco.name) {
        const searchQuery = bloco.name + " bloco de carnaval 2024";
        const googleUrl = `https://www.google.com/search?q=${searchQuery}`;
        open(googleUrl);
      }
    },
  },
};
</script>

<style scoped lang="scss">
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  align-items: center;
  justify-content: center;
}

.card-block {
  margin-top: 4.15rem;
  gap: 3.2rem;
  width: 38.4rem;
  height: 32.3rem;
  padding: 1.6rem;
  border-radius: 1rem;
  border: 0.1rem solid #eaeaea;
  background: #fff;
}

img {
  width: 35rem;
  height: 15.3rem;
  cursor: pointer;
  will-change: filter;
  transition: filter 300ms, transform 300ms;
  &:hover {
    filter: brightness(0.8);
    transform: translateY(-5px);
  }
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
