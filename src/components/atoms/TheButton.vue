<template>
  <button
    id="purple-button"
    class="purple-button"
    :class="{ white: variant === 'white', big: big }"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "TheButton",
  props: {
    variant: {
      type: String,
      default: "purple",
    },
    big: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style scoped lang="scss">
.purple-button {
  background-color: $purple;
  color: $white;
  padding: 0.5rem 3rem;
  border: none;
  border-radius: 0.5rem;
  cursor: pointer;
  text-transform: uppercase;
  font-weight: 500;
  font-size: 14px;

  &:hover {
    opacity: 0.9;
  }

  &.white {
    background-color: $white;
    color: $purple;
  }

  &.big {
    padding: 1.2rem 3.2rem;
    font-size: 1.6rem;
  }
}

.container-center {
  display: flex;
  justify-content: center;
  align-items: center;
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
</style>
