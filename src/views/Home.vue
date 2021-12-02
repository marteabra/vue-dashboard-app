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
.homepage {
  display: flex;
  margin-top: 3em;
  width: 100%;
  justify-content: space-evenly;
}

.homepage__slideshow {
  margin-top: 2.8em;
}

.homepage__todo {
  margin-top: 2.8em;
}
</style>