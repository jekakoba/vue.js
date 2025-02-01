<template>
  <div>
    <label>
      <input
        type="text"
        placeholder="Type a new message"
        v-model.trim="userText"
      />
    </label>
    <button :disabled="isEmptyField" @click="addItem">Send</button>
  </div>
</template>

<script>
export default {
  name: "InputText",
  data() {
    return {
      userText: null,
    };
  },
  methods: {
    addItem() {
      this.$emit("addItem", this.userText);
      this.userText = "";
    },
  },
  computed: {
    isEmptyField() {
      return !this.userText;
    },
  },
};
</script>

<style scoped>
</style>