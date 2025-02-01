<template>
  <input-text @addItem="createItem" />
  <messenger-item
    v-for="item in data"
    :key="item.id"
    :message-list="item"
    @like="onChangeLikes"
  />
</template>

<script>
import InputText from "./InputText.vue";
import MessengerItem from "./MessengerItem.vue";
export default {
  name: "MessengerBlock",
  components: { InputText, MessengerItem },
  data() {
    return {
      data: [],
    };
  },
  methods: {
    createItem(userText) {
      this.data.push({
        id: new Date().getTime(),
        userText,
        likes: 0,
      });
    },
    onChangeLikes({ searchId, num }) {
      let item = this.data.find((item) => item.id === searchId);
      item.likes += num;
    },
  },
};
</script>

<style scoped>
</style>