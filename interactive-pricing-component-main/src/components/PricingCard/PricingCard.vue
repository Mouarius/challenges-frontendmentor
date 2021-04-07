<template>
  <div class="card">
    <div class="card-content card-body">
      <pricing-card-header views="100" price="10" />
      <base-slider></base-slider>
      <footer class="controls">
        <div class="option option-left">Monthly Billing</div>
        <base-switch-button class="switch" />
        <div class="option option-right">
          <span class="option-text">Yearly Billing</span>
          <span class="tag">25% discount</span>
        </div>
      </footer>
    </div>

    <footer class="card-content">
      <ul>
        <li>100% data ownership</li>
        <li>Unlimited websites</li>
        <li>Email reports</li>
      </ul>
      <base-button>Start my trial</base-button>
    </footer>
  </div>
</template>

<script>
import PricingCardHeader from "./PricingCardHeader.vue";
import BaseSlider from "../UI/BaseSlider.vue";
import BaseSwitchButton from "../UI/BaseSwitchButton.vue";
import BaseButton from "../UI/BaseButton.vue";

export default {
  components: { PricingCardHeader, BaseSlider, BaseSwitchButton, BaseButton },
  data() {
    return {
      price: "16.00",
      views: 100,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

$text-primary: hsl(225, 20%, 60%);
$text-secondary: hsl(227, 35%, 25%);

footer.controls {
  font-size: 12px;
  display: grid;
  justify-content: center;
  align-content: center;
  grid-template-columns: 1fr 50px 1fr;
  column-gap: 10px;
  margin: 30px 0;
  .switch {
    margin: 0 0.8em;
  }
}
.option-right {
  place-self: left;
  justify-self: stretch;
}
.option-left {
  text-align: right;
}
.tag {
  font-size: 10px;
  line-height: 10px;
  padding: 0 4px;
  border-radius: 5px;
  align-items: center;
  text-align: center;
  background: $discount-bg;
  color: $discount-text;
  margin-left: 0.5em;
}

.card {
  color: $text-primary;
  display: flex;
  flex-direction: column;
  margin: auto;
  width: 540px;
  border-radius: 10px;
  font-size: 0.95em;
  box-shadow: 0 10px 50px -18px rgba($color: #000000, $alpha: 0.3);
  .card-body {
    border-bottom: solid 1px rgba($color: #000000, $alpha: 0.1);
    padding-top: 3em;
  }
}

.card-content {
  padding: 0 3em;
}
.card > footer {
  padding-top: 2em;
  padding-bottom: 2em;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
ul {
  padding-left: 1em;
}
li {
  list-style: url("../../assets/images/icon-check.svg");
  // padding-left: 0.5em;
}
</style>
