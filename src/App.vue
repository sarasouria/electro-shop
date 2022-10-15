<script setup>
import { RouterLink, RouterView } from 'vue-router';

import Navbar from './components/Navbar.vue';
import MyFooter from './components/MyFooter.vue';
components:{
  Navbar,
  MyFooter
}
</script>

<template>
  <Navbar />
  <RouterView />
  <MyFooter />
</template>




