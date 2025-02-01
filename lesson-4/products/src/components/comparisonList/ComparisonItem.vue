<template>
  <li class="comparison-list__image">
    <img :src="imagesList.src" alt="image" />
  </li>
</template>

<script>
export default {
  name: "ComparisonItem",
  props: {
    imagesList: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.comparison-list__image {
  position: relative;
  width: 50px;
  height: 50px;
  img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
}
</style>