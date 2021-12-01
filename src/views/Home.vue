<template>
  <div class="homepage">
    <ContactForm />
    <Slideshow class="homepage__slideshow" />
  </div>
</template>

<script>
import ContactForm from "../components/ContactForm.vue";
import Slideshow from "../components/Slideshow.vue";

export default {
  components: {
    ContactForm,
    Slideshow,
  },
};
</script>

<style>
.homepage {
  display: flex;
  margin-top: 3em;
}

.homepage__slideshow {
  margin-top: 2.8em;
}
</style>