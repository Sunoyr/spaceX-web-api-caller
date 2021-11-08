<template>
  <AppHeader/>
  <img alt="Vue logo" src="./assets/logo.png">
  <LaunchItem msg="Welcome to Your Vue.js App"/>
  <AppFooter/>
</template>

<script>
import LaunchItem from './components/Launch-Item.vue'
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    LaunchItem,
    AppFooter
  }
}
</script>