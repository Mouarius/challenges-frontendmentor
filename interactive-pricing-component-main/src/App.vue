<template>
  <div>
    <PageTitle />
    <PricingCard></PricingCard>
  </div>
</template>

<script>
import PricingCard from "./components/PricingCard/PricingCard.vue";
import PageTitle from "./components/PageTitle.vue";

export default {
  data() {
    return {
      name: "Vue",
    };
  },
  components: {
    PricingCard,
    PageTitle,
  },
};
</script>
