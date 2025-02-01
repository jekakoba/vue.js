<template>
  <div class="product-card">
    <a class="product-card__image" :href="productsList.link">
      <img :src="productsList.image" :alt="productsList.title" />
    </a>
    <a class="product-card__title" :href="productsList.link">{{
      productsList.title
    }}</a>
    <div class="product-card__availability">
      <span v-if="isAvailability" style="color: green">Є в наявності</span>
      <span v-else style="color: gray">Нема в наявності</span>
    </div>
    <div class="product-card__prices">
      <div v-if="isOldPrice" class="product-card__old-price">
        {{ productsList.oldPrice }} <span>{{ productsList.currency }}</span>
      </div>
      <div class="product-card__price" :class="{ discount: isOldPrice }">
        {{ productsList.price }} <span>{{ productsList.currency }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: {
    productsList: {
      type: Object,
      default: () => ({}),
    },
  },
  computed: {
    isAvailability() {
      return this.productsList.isAvailability;
    },
    isOldPrice() {
      return this.productsList.oldPrice;
    },
  },
};
</script>

<style lang="scss" scoped>
.product-card {
  display: flex;
  flex-direction: column;

  // .product-card__image

  &__image {
    position: relative;
    padding-bottom: 100%;
    margin-bottom: 20px;
    img {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      object-fit: contain;
    }
  }

  // .product-card__title

  &__title {
    font-size: 14px;
    margin-bottom: 10px;
    @media (any-hover: hover) {
      &:hover {
        text-decoration: underline;
      }
    }
  }

  // .product-card__availability

  &__availability {
    span {
      display: block;
    }
  }

  // .product-card__prices

  &__prices {
    font-size: 20px;
  }

  // .product-card__price

  &__price {
    font-weight: 700;
  }

  // .product-card__old-price

  &__old-price {
    color: grey;
    text-decoration: line-through;
    font-size: 18px;
  }
}
.discount {
  color: red;
}
</style>