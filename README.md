# event-bus

## main.js
```javascript
import Vue from 'vue'
...
Vue.prototype.$EventBus = new Vue();
...
```

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

## Run: yarn serve
<img alt="Vue logo" src="https://lh3.googleusercontent.com/__p11jZyT77dNkUYmqb9TJJ11ZObwDsZlwXArCoMrRx22n0amE280PPHQZm_WaXBAE9lbwGKUZ7nxsXFA1czg16emA5HI2mUVsoXoQvkpph6E7-XYYo38iR7QIcWpLwvL9IEwOuHBo59y-OKH2VX3JjQE0U7Aw6w2PQzykP38e3d6xXb0fFi5HThK3rcTqKbcbBBCTE8_uGfc0usOpfkgyVa_uB1ledywCCwlv7Xcl8Yti5ge66T71utaBj77qyyeswJ9XyIv0cupyD3wfv7a0-if0ggpIbyneSn9Tled3o_c3p6ap5xRWgsteZvSGV0eyVExjGBvSq4xrhq_qkCZDKsHyi-ONgMrVtRoDxu3hYuUf2sx3VCLppUGC8SenlBDXooZAw0jj_cveYSTNseosPEGOqQTIOWeR40J-HRPE7HOma0ifv-jf9mfGIuajmjj6_qkznfFAnAhuTD9JEGkKyyyw6t8Blr_zIf-glx5hP_f5sUsE8MOh1VYBSElTIWYZc_BRhCT_gNoFRh5qDClphyV4jyB1U344IwSzth583JXI5dvKkO4aprs3rzgMikT_TAMA0g1-ciYbn9M_ODkJgMLnAwQYkQz5AjIla7_qfn7_yjsbSu1852FF5UXwWPPvGNOBXJXqMpa6FHFj4maPmT02HKbdh_TTtsBz8nsPMentG7-kVQ5aJAz6Vn=w380-h269-no?authuser=0" />

## Click Button in Body.vue
<img alt="Vue logo" src="https://lh3.googleusercontent.com/1GdDI3RG3SvjnPmQuOa9rK_IuQkeQwYjo8x3KrisRRnpwwRfAyYxYCA0-zoRMDBKgH4eEc1AW2fo8v5B7C3z3NKCjj2uo7ugD6Srs7rfuVwrWZPz5dumtAyiFwcQ_55i3DHIqzEfdpbCgWaF2E190Z4PMerxVKEl8ZGlmgTADNHgozb-B1cWjbJP9xMnx5ePOG1qU8qKTXz9aswn9r-N4PXYiqu4pu4jNDhs169g36S56twnZQtIah-h_M5WVr2p-WnzLjdgdyX1p0chaunZlNM17gokWozMCtJzWgm7qp2NzK3U93MZZvU2F-1jq2EgeA8SFM9zg3o2Rxn6aiZ2W2Bo6Hkk77N0-NjYspNpwm-cEqdPHJQ0gmsv7cfR7i27s7MGmIoM94fLOLBS-wgjl2NvCpIgx66iRwzIImJNWLb9UlDIPZxcaXNyFbKvmt7kM00Eirsrvr8gRRVShdhn-Du0dlOC2kwflysw9eqIxwtZO8gG3t6Bio2yg9fXyRgrqrsiiXLyh_q9KHloq9Osg1UWpt2TYrHlKPu0x2xNkOZnuXJnsru2xdLQiHJex8ywqaTz_cnuGOCmFtQ8lggfEE5iWMmze_-D-756KtxbGxmq1HTgkfW1dItjhUMuTzKabAMIK0z0lbqcqOOWhx9aQZ872DG2PBQV5zJS9VlKyT8LEqj4k64xtxgMfdI3=w748-h250-no?authuser=0" />