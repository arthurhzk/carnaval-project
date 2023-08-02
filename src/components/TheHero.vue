<template>
  <div class="main-container">
    <div class="content">
      <the-titles></the-titles>
      <the-inputs></the-inputs>
    </div>
  </div>
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
.main-container {
  min-height: 53.2rem;
  text-align: center;
  position: relative;
  background-color: $bg-gray;
  z-index: 1;
}
.main-container::before {
  content: "";
  background-image: url(../assets/bg-header-top.svg);
  width: 40.7rem;
  height: 34.5rem;
  position: absolute;
  z-index: 0;
  top: 0;
  left: 0;
}
.main-container::after {
  content: "";
  background-image: url(../assets/bg-header-bottom.svg);
  width: 41.4rem;
  height: 33rem;
  position: absolute;
  right: 0;
  bottom: -1rem;
  overflow: hidden;
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
  .main-container::before,
  .main-container::after {
    display: none;
  }
}
</style>
