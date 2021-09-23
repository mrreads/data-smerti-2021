<template>
  <router-view/>
</template>

<script>
import AOS from './assets/lib/aos';
import './assets/lib/aos.css';

import './assets/css/general.css';
import './assets/css/test.css';
import './assets/css/media.css';

export default {
  name: 'App',
  created() {
    AOS.init();
  }
}
</script>