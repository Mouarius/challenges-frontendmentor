<template>
  <div>
    <div class="bar-container">
      <div class="bar-empty bar"></div>
      <div class="bar-full bar" v-bind:style="fullBarStyle"></div>
      <input @input="updateSlider" type="range" min="0" max="100" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sliderValue: 50,
    };
  },
  computed: {
    fullBarStyle() {
      return {
        width: `${this.sliderValue}%`,
      };
    },
  },
  methods: {
    updateSlider(e) {
      this.sliderValue = e.target.value;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

$track-w: 100%;
$track-h: 0.4em;
$thumb-d: 1.9em;
$track-c: $empty-slider;
$filll-c: $full-slider;

@mixin track($fill: 0) {
  box-sizing: border-box;

  // @if $fill == 1 {
  //   .js & {
  //     background: linear-gradient($filll-c, $filll-c)
  //       0 /
  //       var(--sx)
  //       100%
  //       no-repeat
  //       $track-c;
  //   }
  // }
}
.test {
  height: 40px;
  width: 40px;
}

@mixin fill() {
  height: $track-h;
  background: $filll-c;
  border-radius: ($track-h/2);
}

@mixin thumb() {
  box-sizing: border-box;
  cursor: pointer;
  width: $thumb-d;
  height: $thumb-d;
  border-radius: 50%;
  // background: $slider-handle;
  background: $slider-handle url("../../assets/images/icon-slider.svg")
    no-repeat center/60%;
  transition: all 0.2s;
  box-shadow: 0 8px 15px 0px rgba($color: $full-slider, $alpha: 0.8);
  &:hover {
    box-shadow: 0 9px 15px 3px rgba($color: $full-slider, $alpha: 0.8);
    transform: scale(1.1);
  }
}

.bar-container {
  position: relative;
  height: $thumb-d;
}
.bar {
  @include fill();
  background-color: $empty-slider;
  position: absolute;
  top: 5px;
}
.bar-empty {
  width: 100%;
}
.bar-full {
  background-color: $full-slider;
}

[type="range"] {
  &,
  &::-webkit-slider-thumb {
    -webkit-appearance: none;
  }

  --range: calc(var(--max) - var(--min));
  --ratio: calc((var(--val) - var(--min)) / var(--range));
  --sx: calc(0.5 *#{$thumb-d} + var(--ratio) * (100% - #{$thumb-d}));
  margin: 0;
  padding: 0;
  position: absolute;
  width: $track-w;
  height: $thumb-d;
  background: transparent;

  &:focus {
    outline: none;
  }

  &::-webkit-slider-runnable-track {
    @include track(1);
  }
  &::-moz-range-track {
    @include track;
  }
  &::-ms-track {
    @include track;
  }

  &::-moz-range-progress {
    @include fill;
  }
  &::-ms-fill-lower {
    @include fill;
  }

  &::-webkit-slider-thumb {
    margin-top: 0.5 * ($track-h - $thumb-d);
    @include thumb;
  }
  &::-moz-range-thumb {
    @include thumb;
  }
  &::-ms-thumb {
    margin-top: 0;
    @include thumb;
  }

  &::-ms-tooltip {
    display: none;
  }
}
</style>
