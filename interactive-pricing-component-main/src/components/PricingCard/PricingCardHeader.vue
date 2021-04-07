<template>
  <header>
    <span class="page-views">{{ views }}K Pageviews</span>
    <span class="pricing"
      ><strong>${{ price }}</strong> /month</span
    >
  </header>
</template>

<script>
export default {
  props: ["views", "price"],
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
header {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  .page-views {
    text-transform: uppercase;
    font-size: 0.8rem;
  }
  .pricing {
    display: flex;
    flex-direction: row;
    align-items: center;
    strong {
      font-size: 2.1rem;
      font-weight: 800;
      color: $text-dark;
      margin-right: 0.2em;
    }
  }
}
</style>
