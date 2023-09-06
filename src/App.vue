<script setup>
import AppHeader from './components/AppHeader.vue';

</script>

<template>
  <AppHeader />
  <router-view>

  </router-view>
  
</template>

<style lang="scss">
  @import '../node_modules/bootstrap/scss/bootstrap';
  @import './style/general.scss'
</style>
