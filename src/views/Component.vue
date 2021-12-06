<template>
   <ToDo v-if="$route.params.component_id == 'todo'"/>
   <Slideshow v-if="$route.params.component_id == 'slideshow'"/>
   <Table v-if="$route.params.component_id == 'table'"/>
   <Quiz v-if="$route.params.component_id == 'quiz'"/>
   <ContactForm v-if="$route.params.component_id == 'contact'"/>
</template>

<script>
import ToDo from '../components/ToDo.vue';
import Slideshow from '../components/Slideshow.vue';
import Table from '../components/Table.vue';
import Quiz from '../components/Quiz.vue';
import ContactForm from '../components/ContactForm.vue';

export default {
   components: {
      ToDo,
      Slideshow,
      Table,
      Quiz,
      ContactForm
   },

   data() {
      return {};
   }
}

   </script>