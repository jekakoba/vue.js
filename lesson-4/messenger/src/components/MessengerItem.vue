<template>
  <div class="messenger-item">
    <p>{{ messageList.userText }}</p>
    <div>
      <button @click="onLike">Like</button>
      <button @click="onDislike" :disabled="invalidValue">Dislike</button>
    </div>
    <div>
      Likes: <span>{{ messageList.likes }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "MessengerItem",
  props: {
    messageList: {
      type: Object,
      default: () => ({}),
    },
  },
  methods: {
    onLike() {
      this.$emit("like", { searchId: this.messageList.id, num: 1 });
    },
    onDislike() {
      this.$emit("like", { searchId: this.messageList.id, num: -1 });
    },
  },
  computed: {
    invalidValue() {
      return !this.messageList.likes;
    },
  },
};
</script>
<style scoped>
.messenger-item {
  display: flex;
  align-items: center;
  gap: 10px;
}
.messenger-item button {
  cursor: pointer;
}
</style>
