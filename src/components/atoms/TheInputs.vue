<template>
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
      <TheButton @click="searchCityOnGoogle">{{ purpleButton }}</TheButton>
    </div>
  </div>
</template>

<script>
import TheButton from "../atoms/TheButton.vue";
export default {
  name: "TheInputs",
  data() {
    return {
      title: `Encontre os <span class="roxo">melhores blocos</span> <br> de carnaval de 2024`,
      subTitle: "Find your block",
      selectedCity: "",
      cities: [
        { label: "Selecione uma cidade", value: "" },
        { label: "Roca Sales - RS", value: "roca sales" },
        { label: "Encantado - RS", value: "encantado" },
        { label: "Arvorezinha - RS", value: "arvorezinha" },
        { label: "Guaporé - RS", value: "guaporé" },
        { label: "Lajeado - RS", value: "lajeado" },
      ],
      purpleButton: "Buscar agora",
    };
  },
  methods: {
    searchCityOnGoogle() {
      if (this.selectedCity === "") {
        alert("Selecione uma opção!");
      } else if (this.selectedCity) {
        const searchQuery = this.selectedCity + " bloco de carnaval 2024";
        const googleUrl = `https://www.google.com/search?q=${searchQuery}`;
        open(googleUrl);
      }
    },
  },
  components: { TheButton },
};
</script>

<style lang="scss" scoped>
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
  margin-top: 4rem;
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
</style>
