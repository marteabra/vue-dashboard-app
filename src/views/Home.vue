<template>
  <div class="homepage">
    <Slideshow class="homepage__slideshow" /> 
    <div class="homepage__infobox">
      <div class="homepage__infobox--content">
        <h3 class="content__title">HELLO</h3>
        <div class="content__paragraphs">
          <p>Welcome to our component page!</p>
          <p>
            Here you will find components for everyday use.</p> 
            <p>Feel free to use the To do list when shopping, or the slideshow if you
            feel the need to look at some cool images. This page will also
            provide you with a cool sortable table with useless information. You
            should also try to get a full score on our quiz. 
            <p>If you have any
            questions about our page, please send us a message through our
            contact form(we will not read it).</p> 
            <br>
            <p>- Marte & Mayo</p>
          </p>
        </div>
      </div>
    </div>
    <Table />
    <ToDo class="homepage__todo" />
    <Quiz />
    <ContactForm />
  </div>
</template>

<script>
import ContactForm from "../components/ContactForm.vue";
import Slideshow from "../components/Slideshow.vue";
import ToDo from "../components/ToDo.vue";
import Table from "../components/Table.vue";
import Quiz from "../components/Quiz.vue";

export default {
  components: {
    ContactForm,
    Slideshow,
    ToDo,
    Table,
    Quiz,
  },
};
</script>

<style>
.homepage {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-column-gap: 1em;
  grid-row-gap: 1em;
  margin: 4em 1em 2em 1em;
  width: 100%;
}

.homepage__infobox {
  position: relative;
  background: rgb(37, 37, 37);
  width: 30vw;
  padding: 1em;
}

.homepage__infobox--content {
  color: white;
  height: 50vh;
}

.content__paragraphs {
  text-align: center;
  padding: 1em;
}
</style>