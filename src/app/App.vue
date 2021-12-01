<template>
  <Header />
  <RouterView />
</template>

<script>
import Header from "../components/Header.vue";

export default {
  components: {
    Header,
  },
};
</script>

<style>
@import "../styles/reset.css";
@import "../styles/variables.css";
@import "../styles/style.css";
</style>