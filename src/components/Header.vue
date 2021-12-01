<template>
  <header class="header">
    <nav class="header__nav">
      <span><RouterLink to="{ name: `home` }">Home</RouterLink></span>
      <span><RouterLink to="{ name: `slideshow` }">Slideshow</RouterLink></span>
      <span><RouterLink to="{ name: `table` }">Table</RouterLink></span>
      <span><RouterLink to="{ name: `quiz` }">Quiz</RouterLink></span>
      <span><RouterLink to="{ name: `todo` }">To do List</RouterLink></span>
      <span><RouterLink to="{ name: `contact` }">Contact</RouterLink></span>
    </nav>
  </header>
</template>

<script>
export default {
  methods: {
    push() {
      this.$router.push("/");
    },

    replace() {
      this.$router.replace("/");
    },
  },
};
</script>

<style>
.header__nav {
  background: white;
  position: relative;
  display: flex;
  width: 100%;
}

.header__nav span {
  background: rgb(181, 181, 238);
  position: absolute;
}
</style>