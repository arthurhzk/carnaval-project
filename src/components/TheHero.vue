<template>
  <header>
    <div class="content">
      <div class="title">
        <p class="subtitle">{{ subTitle }}</p>
        <h1 class="main-title" v-html="title"></h1>
      </div>
      <div class="search-content">
        <div class="search-field">
          <input
            class="input-content"
            type="text"
            placeholder="Pesquise por nome"
          />
          <select class="select-content" v-model="selectedCity">
            <option
              v-for="(city, index) in cities"
              :key="index"
              :value="city.value"
            >
              {{ city.label }}
            </option>
          </select>
          <button class="purple-button">{{ purpleButton }}</button>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "TheHero",
  data() {
    return {
      title: "Encontre os melhores blocos <br> de carnaval de 2023",
      subTitle: "Find your block",
      selectedCity: "",
      cities: [
        { label: "Selecione uma cidade", value: "" },
        { label: "Roca Sales - RS", value: "opcao1" },
        { label: "Encantado - RS", value: "opcao2" },
        { label: "Arvorezinha - RS", value: "opcao3" },
        { label: "Guaporé - RS", value: "opcao4" },
        { label: "Lajeado - RS", value: "opcao5" },
      ],
      purpleButton: "Buscar agora",
    };
  },
};
</script>
<style scoped lang="scss">
header {
  min-height: 53.2rem;
  min-width: 144rem;
  text-align: center;
  position: relative;
  background-color: $bg-gray;
  z-index: 1;
}
header::before {
  content: "";
  background-image: url(../assets/bg-header-top.svg);
  width: 40.7rem;
  height: 34.5rem;
  position: absolute;
  z-index: 0;
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
.search-content {
  padding: 4rem;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3.2rem;
  background-color: $white;
  max-width: 99.3rem;
  max-height: 12.8rem;
  margin: auto;
}
.search-field {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1.2rem;
  gap: 2.4rem;
  min-width: 25.4rem;
  min-height: 1.6rem;
  border-radius: 0.5rem;
}
.input-content,
.select-content {
  background: $bg-gray;
  color: $gray1;
  font-size: 1.6rem;
  font-style: normal;
  font-weight: 400;
  line-height: 100%;
  border: none;
  padding: 1.2rem;
}
.purple-button {
  background-color: $purple;
  color: $white;
  padding: 1.2rem 3.2rem;
  border: none;
  border-radius: 0.5rem;
  cursor: pointer;
  text-transform: uppercase;
  font-weight: 500;
  font-size: 14px;
}
.purple-button:hover {
  opacity: 0.9;
}
</style>
