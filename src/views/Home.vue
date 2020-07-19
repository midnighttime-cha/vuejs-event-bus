<template>
  <div class="home">
    <Header />
    <Body />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import HelloWorld from "@/components/Body.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "Home",
  components: {
    Header,
    Body,
    Footer
  }
};
</script>
