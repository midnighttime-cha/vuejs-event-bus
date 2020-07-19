# event-bus

## Create Component: Body.vue
```javascript
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
```

## Create Component: Header.vue
```javascript
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

## Create Component: Footer.vue
```javascript
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
```