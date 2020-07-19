# event-bus

## Create Component: Header
```vuejs
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
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
