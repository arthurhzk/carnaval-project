<template>
  <div class="title">
    <p class="subtitle">{{ subTitle }}</p>
    <h1 class="main-title" v-html="title"></h1>
  </div>
</template>

<script>
export default {
  name: "TheTitles",
  data() {
    return {
      title: `Encontre os <span class="roxo">melhores blocos</span> <br> de carnaval em 2024`,
      subTitle: "Find your block",
    };
  },
};
</script>

<style scoped lang="scss">
.title {
  gap: 1.9rem;
  align-items: center;
}
.subtitle {
  padding-top: 10rem;
  text-transform: uppercase;
  color: $orange;
  font-size: 1.6rem;
  font-weight: 500;
  line-height: 160%;
  letter-spacing: 1.6px;
}
.main-title {
  font-size: 4.8rem;
  font-weight: 700;
  line-height: 125%;
  color: $black;
}
</style>
