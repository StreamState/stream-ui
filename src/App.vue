<template>
  <div>
    <Navbar />
    <router-view />
    <Footer />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Footer from "@/components/Footer.vue";

// eslint-disable-next-line no-unused-vars

export default {
  name: "App",
  components: {
    Navbar, 
    Footer
  },
  data: function () {
    return {};
  },
  methods: {},
  mounted() {},
};
</script>

<style lang="scss">
</style>
