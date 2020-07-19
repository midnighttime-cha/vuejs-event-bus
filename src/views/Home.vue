<template>
  <div class="home">
    <Header />
    <HelloWorld />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import HelloWorld from "@/components/HelloWorld.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "Home",
  components: {
    Header,
    HelloWorld,
    Footer
  }
};
</script>
