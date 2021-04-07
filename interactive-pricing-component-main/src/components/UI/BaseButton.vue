<template>
  <button><slot></slot></button>
</template>

<script>
export default {
  name: "BaseButton",
  props: ["name"],
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
button {
  border: none;
  background: $text-dark;
  color: $cta-text;
  font-size: 12px;
  width: 170px;
  height: 40px;
  border-radius: 20px;
  transition: all 0.2s;
  cursor: pointer;
  &:hover {
    transform: scale(1.02);
    box-shadow: -3px 3px 5px rgba($color: $text-dark, $alpha: 0.1);
  }
}
</style>
