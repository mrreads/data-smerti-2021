<template>
  <Langing> </Langing>
</template>

<script>
import AOS from 'aos'
import 'aos/dist/aos.css'

import './assets/css/general.css';
import './assets/css/media.css';

import Langing from './components/Landing.vue'

export default {
  name: 'App',
  components: {
    Langing
  },
  created () {
    AOS.init()
  }
}
</script>