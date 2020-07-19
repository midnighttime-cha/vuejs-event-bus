<template>
  <div>
    <strong>
      <font size="8px">Body: {{text}}</font>
    </strong>
    <br />
    <button @click="onEvent()">Click Here..</button>
  </div>
</template>

<script>
export default {
  data: () => ({
    text: "Hello Bangkok"
  }),

  methods: {
    onEvent() {
      this.$EventBus.$emit("hello-bangkok", this.text);
    }
  }
};
</script>

<style>
</style>