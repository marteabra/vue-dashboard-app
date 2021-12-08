<template>
  <header class="topnav">
      <span><RouterLink :to="{ name: 'home' }">Home</RouterLink></span>
      <span><RouterLink :to="{ name: 'component', params: { component_id: 'slideshow' } }">Slideshow</RouterLink></span>
      <span><RouterLink :to="{ name: 'component', params: { component_id:  'table' } }">Table</RouterLink></span>
      <span><RouterLink :to="{ name: 'component', params: { component_id: 'quiz' } }">Quiz</RouterLink></span>
      <span><RouterLink :to="{ name: 'component', params: { component_id: 'todo' } }">To do List</RouterLink></span>
      <span><RouterLink :to="{ name: 'component', params: { component_id: 'contact' } }">Contact Us</RouterLink></span>
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
header {
  width: auto;
  display: flex;
  padding: 0px 10px;
  margin: 10px 10px;
  color: white;
  position: relative;
  overflow: hidden;
  background-color:grey;
}

span {
  text-align: center;
  padding: 0px 10px;
  text-decoration: none;
  font-size: 20px;
}

span:hover {
  background-color: #ddd;
}

span:active {
  background-color: purple;
}


span .router-link-active {
  color: white

}

</style>