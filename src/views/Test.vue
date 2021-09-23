<template>

  <Questions2 v-if="currentQuestion == 2"></Questions2>
  <Questions3 v-if="currentQuestion == 3"></Questions3>

  
</template>

<script>
import Questions2 from '../components/Question-2.vue';
import Questions3 from '../components/Question-3.vue';

import './../assets/css/test.css';

export default {
   components: {
    Questions2,
    Questions3
  },

  data() {
      return {
        currentQuestion: 2,
        allQuestion: 5
      }
  }
}
</script>
