<template>
  <div class="homepage">
  <div class="homepage__slideshow homepage__component" >
    <Slideshow /> 
  </div>  
  
    <div class="homepage__infobox homepage__component">
      <div class="homepage__infobox--content">
        <h3 class="content__title">HELLO</h3>
        <div class="content__paragraphs">
            <p>Welcome to our component page!</p>
            <p>Here you will find components for everyday use.</p> 
            <p>Feel free to use the To do list when shopping, or the slideshow if you
              feel the need to look at some cool images. This page will also
              provide you with a cool sortable table with useless information. You
              should also try to get a full score on our quiz. 
            <p>If you have any questions about our page, please send us a message through our
              contact form(we will not read it).</p> 
              <br>
            <p>- Marte & Mayo</p>
            </p>
        </div>
      </div>
    </div>
    
    <div class="homepage__table homepage__component">
      <Table />
    </div>

    <div class="homepage__todo homepage__component" >
      <ToDo />
    </div>

    <div class="homepage__quiz homepage__component">
      <Quiz />
    </div>

    <div class="homepage__contactform homepage__component">
      <ContactForm />
    </div>
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
  grid-row-gap: 2em;
  margin-top: 4em;
  width: 100%;
  margin: 40px 20px 20px 20px;
}

.homepage__component {
  border: 1px solid black;
  border-radius: 1em;
  width: 30vw;
}

.homepage__infobox {
  background: rgb(37, 37, 37);
  position: relative;
  border: none;
  width: 30vw;
  height: 60vh;
  padding: 1em;
}

.homepage__infobox--content {
  color: white;
  height: 50vh;
  margin-top: 4em;
  border-radius: 1em;
}

.content__paragraphs {
  text-align: center;
  padding: 1em;
}

.homepage__todo {
  background: rgb(37, 37, 37);
}
</style>