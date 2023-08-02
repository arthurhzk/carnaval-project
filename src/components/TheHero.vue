<template>
  <header>
    <div class="content">
      <the-titles></the-titles>
      <the-inputs></the-inputs>
    </div>
  </header>
</template>

<script>
import TheInputs from "../components/atoms/TheInputs.vue";
import TheTitles from "./TheTitles.vue";
export default {
  name: "TheHero",
  components: {
    TheInputs,
    TheTitles,
  },
  data() {
    return {
      title: `Encontre os <span class="roxo">melhores blocos</span> <br> de carnaval de 2023`,
      subTitle: "Find your block",
    };
  },
};
</script>
<style scoped lang="scss">
header {
  min-height: 53.2rem;
  text-align: center;
  position: relative;
  background-color: $bg-gray;
  z-index: -2;
}
.content {
  z-index: 1;
}
header::before {
  content: "";
  background-image: url(../assets/bg-header-top.svg);
  width: 40.7rem;
  height: 34.5rem;
  position: absolute;
  z-index: -1;
  top: 0;
  left: 0;
}
header::after {
  content: "";
  background-image: url(../assets/bg-header-bottom.svg);
  width: 41.4rem;
  height: 33rem;
  position: absolute;
  right: 0;
  bottom: -1rem;
  overflow: hidden;
  z-index: 0;
}
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
  font-style: normal;
  font-weight: 700;
  line-height: 125%;
  color: $black;
}

@media (max-width: 700px) {
  header::before,
  header::after {
    display: none;
  }
}
</style>
