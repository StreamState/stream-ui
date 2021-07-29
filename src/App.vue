<template>
  <div>
    <Navbar />
    <router-view />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
// eslint-disable-next-line no-unused-vars

export default {
  name: "App",
  components: {
    Navbar,
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
