<template>
  <div class="homepage">
    <ContactForm />
    <Slideshow class="homepage__slideshow" />
    <ToDo class="homepage__todo" />
  </div>
</template>

<script>
import ContactForm from "../components/ContactForm.vue";
import Slideshow from "../components/Slideshow.vue";
import ToDo from "../components/ToDo.vue";

export default {
  components: {
    ContactForm,
    Slideshow,
    ToDo,
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