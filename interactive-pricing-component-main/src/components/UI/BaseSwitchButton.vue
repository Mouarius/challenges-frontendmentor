<template>
  <div>
    <div class="container" @click="switchState">
      <div class="ball" :class="position"></div>
    </div>
    <input v-bind:value="isChecked" type="checkbox" name="switch" id="switch" />
  </div>
</template>

<script>
export default {
  name: "BaseSwitchButton",
  data() {
    return {
      position: "left",
    };
  },
  computed: {
    isChecked() {
      return this.position === "right";
    },
  },
  methods: {
    switchState() {
      if (this.position === "left") this.position = "right";
      else this.position = "left";
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

$btn-size: 12px;

@mixin circle($size) {
  width: $size;
  height: $size;
  border-radius: 100%;
}
input {
  display: none;
}
.container {
  display: block;
  cursor: pointer;
  box-sizing: content-box;
  width: $btn-size * 2.3;
  height: $btn-size;
  border-radius: $btn-size;
  padding: 3px;
  background: $toggle-bg;
  transition: all 0.2s ease-in-out;

  &:hover {
    background: hsl(223, 50%, 80%);
  }
}
.left {
  transform: translateX(0);
}
.right {
  transform: translateX(120%);
}
.ball {
  @include circle($btn-size);
  background: white;
  position: relative;
  transition: all 0.2s ease-in-out;
}
</style>
