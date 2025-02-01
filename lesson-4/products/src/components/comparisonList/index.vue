<template>
  <ul class="comparisons__list">
    <comparison-item
      v-for="(item, index) in dataComparisonList"
      :key="index"
      :images-list="item"
    />
  </ul>
</template>
<script>
import ComparisonItem from "./ComparisonItem.vue";
export default {
  name: "comparisonList",
  props: {
    dataComparisonList: {
      type: Array,
      default: () => [],
    },
  },
  components: { ComparisonItem },
};
</script>

<style lang="scss" scoped>
.comparisons {
  &__list {
    display: flex;
    align-items: center;
    gap: 20px;
    flex-wrap: wrap;
  }
}
</style>