<template>
  <div class="homepage">
    <ToDo class="homepage__todo" />
    <Slideshow class="homepage__slideshow" />
    <ContactForm />
    <Table />
  </div>
</template>

<script>
import ContactForm from "../components/ContactForm.vue";
import Slideshow from "../components/Slideshow.vue";
import ToDo from "../components/ToDo.vue";
import Table from "../components/Table.vue";

export default {
  components: {
    ContactForm,
    Slideshow,
    ToDo,
    Table,
  },
};
</script>

<style>
template {
  display: block;
  align-content: center;
}

.homepage {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-column-gap: 1em;
  grid-row-gap: 1em;
  margin-top: 3em;
  width: 100%;
  justify-content: center;
}
</style>