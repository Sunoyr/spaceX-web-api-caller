<template>
  <AppHeader/>
  <RocketItem msg="Welcome to Your Vue.js App"/>
  <AppFooter/>
</template>

<script>
import RocketItem from './components/Rocket-Item.vue'
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    RocketItem,
    AppFooter
  }
}
</script>