<template>
  <div class="homepage">
    <ToDo class="homepage__todo" />
    <Slideshow class="homepage__slideshow" />
    <ContactForm />
    <Table />
    <NewQuiz />
  </div>
</template>

<script>
import ContactForm from "../components/ContactForm.vue";
import Slideshow from "../components/Slideshow.vue";
import ToDo from "../components/ToDo.vue";
import Table from "../components/Table.vue";
import Quiz from "../components/Quiz.vue"


export default {
  components: {
    ContactForm,
    Slideshow,
    ToDo,
    Table,
    NewQuiz,
  },
};
</script>

<style>
.homepage {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-column-gap: 1em;
  grid-row-gap: 1em;
  margin-top: 3em;
  width: 100%;
  align-self: center;
}
</style>