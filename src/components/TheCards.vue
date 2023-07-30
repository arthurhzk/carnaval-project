<template>
  <div class="grid-container">
    <div class="card-block" v-for="bloco in blocos" :key="bloco.id">
      <img v-if="imgMap[bloco.id]" :src="imgMap[bloco.id]" alt="Blocos Image" />
      <div class="loading" v-else>{{ loader }}</div>
      <h3>{{ bloco.name }}</h3>
      <p>{{ bloco.description }}</p>
      <p>{{ bloco.location }}</p>
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
};
</script>

<style scoped>
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
  width: 350px;
  height: 153px;
}
</style>
