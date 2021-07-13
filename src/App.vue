<template>
  <div>
    <Navbar :user="user" @logout="logout" />
    <b-container fluid>
      <router-view :user="user" />
    </b-container>
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
    return {
      user: null,
    };
  },
  methods: {},
  mounted() {},
};
</script>

<style lang="scss">
</style>
