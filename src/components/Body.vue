<template>
  <div>
    <strong>
      <font size="8px">Body: {{textBody}}</font>
    </strong>
    <br />
    <button @click="onEvent()">Click Here..</button>
  </div>
</template>

<script>
export default {
  data: () => ({
    textBody: "?"
  }),

  methods: {
    onEvent() {
      this.textBody = "Hello Bangkok";
      this.$EventBus.$emit("hello-bangkok", this.textBody);
    }
  }
};
</script>