<template>

  <Loader v-if="loaderVisible"></Loader>

  <Questions2 v-if="currentQuestion == 2"></Questions2>
  <Questions3 v-if="currentQuestion == 3"></Questions3>
  <Questions4 v-if="currentQuestion == 4"></Questions4>
  <Questions5 v-if="currentQuestion == 5"></Questions5>
  <Audio v-if="currentQuestion == 6"></Audio>
  
  <Final v-if="currentQuestion == 7"></Final>
</template>

<script>
import Questions2 from '../components/Question-2.vue';
import Questions3 from '../components/Question-3.vue';
import Questions4 from '../components/Question-4.vue';
import Questions5 from '../components/Question-5.vue';

import Audio from '../components/Audio.vue';
import Loader from '../components/Loader.vue';

import Final from '../components/Final.vue';

export default {
   components: {
    Questions2,
    Questions3,
    Questions4,
    Questions5,
    Audio,
    Loader,
    Final
  },

  data() {
      return {
        loaderVisible: false,

        currentQuestion: 2,
        
        userAge: null
      }
  }
}
</script>
