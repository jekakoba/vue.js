<template>
  <div class="container">
    <messenger-block />
  </div>
</template>

<script>
import MessengerBlock from "./components/MessengerBlock.vue";
export default {
  name: "App",
  components: { MessengerBlock },
};
</script>

<style>
* {
  padding: 0px;
  margin: 0px;
}
*,
*::before,
*::after {
  box-sizing: border-box;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  justify-content: center;
  min-height: 100svh;
  max-width: 800px;
  margin: 0 auto;
  font-size: 20px;
  padding: 20px;
}
</style>