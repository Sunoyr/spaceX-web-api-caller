<template>
  <div class="hello">
    <a>{{ info }}</a>
  </div>
</template>

<script>
const axios = require('axios').default;
export default {
  name: 'HelloWorld',
  data() {
    return {
      info: null
    }
  },
  mounted() {
    axios.get('https://api.spacexdata.com/v4/launches')
    .then(response => this.info = response)
    console.log("coucou")
  }
}
</script>