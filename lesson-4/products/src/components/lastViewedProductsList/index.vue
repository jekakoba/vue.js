<template>
  <div class="preview-products__list">
    <product-card
      v-for="prod in lastPreviewProductsList"
      :key="prod.id"
      :products-list="prod"
    />
  </div>
</template>

<script>
import ProductCard from "./ProductCard.vue";
export default {
  components: { ProductCard },
  name: "lastViewedProductsList",
  props: {
    lastPreviewProductsList: {
      type: Object,
      default: () => ({}),
    },
  },
};
</script>

<style lang="scss" scoped>
.preview-products {
  // .preview-products__list
  &__list {
    max-width: 800px;
    display: grid;

    gap: 20px;
    @media (min-width: 767.98px) {
      grid-template-columns: repeat(3, 1fr);
    }
  }
}
</style>