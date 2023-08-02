<template>
  <div>
    <div class="search-content">
      <input
        v-model="selectedInput"
        class="input-content"
        type="text"
        placeholder="Pesquise por bloco"
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
      <TheButton
        :disabled="selectedInput.length == 0 || selectedCity.length == 0"
        @click="searchCityOnGoogle"
        >{{ purpleButton }}</TheButton
      >
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
      selectedInput: "",
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
      const searchQuery =
        this.selectedCity + " " + this.selectedInput + " carnaval 2024";
      const googleUrl = `https://www.google.com/search?q=${searchQuery}`;
      open(googleUrl);
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

  margin: auto;
  margin-top: 4rem;
}
.search-field {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1.2rem;
  gap: 2.4rem;
  max-width: 25.4rem;
  min-height: 1.6rem;
  width: 50%;
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
@media (max-width: 700px) {
  .search-content {
    flex-direction: column;
  }
}
</style>
