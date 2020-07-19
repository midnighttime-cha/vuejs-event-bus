<template>
  <div>
    <strong>
      <font size="8px">Footer: {{textFooter}}</font>
    </strong>
  </div>
</template>

<script>
export default {
  data: () => ({
    textFooter: "?"
  }),
  mounted() {
    this.$EventBus.$on("hello-bangkok", param1 => {
      console.log("Receive event.", param1);
      this.textFooter = param1;
    });
  }
};
</script>