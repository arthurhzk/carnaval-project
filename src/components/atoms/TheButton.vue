<template>
    <button id="purple-button" class="purple-button" :class="{white: variant === 'white', big: big}">
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
        }
    }
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

//   @extend .container-center;
}

.container-center {
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>