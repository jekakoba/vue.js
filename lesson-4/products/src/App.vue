<template>
  <section class="comparisons">
    <div class="comparisons__header">
      <h3>Списки порівнянь</h3>
      <h4>Мобільні телефони:</h4>
      <div>Кількість товарів: {{ comparisonList.length }}</div>
    </div>
    <comparison-list :data-comparison-list="comparisonList" />
  </section>
  <section class="preview-products">
    <h2>Останні переглянуті</h2>
    <last-viewed-products-list
      :last-preview-products-list="lastPreviewProductsList"
    />
  </section>
</template>
<script>
import { dataComparisonList } from "./constants/data_comparison";
import { dataLastPreviewProducts } from "./constants/data_last-viewed-products";
import comparisonList from "./components/comparisonList";
import lastViewedProductsList from "./components/lastViewedProductsList";
export default {
  name: "App",
  components: { comparisonList, lastViewedProductsList },
  computed: {
    comparisonList() {
      return dataComparisonList;
    },
    lastPreviewProductsList() {
      return dataLastPreviewProducts;
    },
  },
};
</script>
<style lang="scss">
a {
  text-decoration: none;
}
body {
  padding: 20px;
  ul li {
    list-style: none;
  }
  ul {
    padding: 0;
  }
  margin: 0;
}
</style>