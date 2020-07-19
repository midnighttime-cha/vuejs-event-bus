<template>
  <div>
    <strong>
      <font size="8px">Header: {{textHeader}}</font>
    </strong>
  </div>
</template>

<script>
export default {
  data: () => ({
    textHeader: "?"
  }),

  mounted() {
    this.$EventBus.$on("hello-bangkok", param1 => {
      console.log("Receive event.", param1);
      this.textHeader = param1;
    });
  }
};
</script>

<style>
</style>