<template>
  <router-view/>
</template>

<script>
const AOS = require('./assets/lib/aos');
import './assets/lib/aos.css';

import './assets/css/general.css';
import './assets/css/test.css';
import './assets/css/media.css';

export default {
  name: 'App',
  mounted() {
    AOS.init();
  }
}
</script>