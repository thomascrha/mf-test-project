<template>
  <div id="app">
  <Show :json='json'> </Show>
  </div>
</template>

<script>
import BootstrapVue from 'bootstrap-vue'

// component
import Show from './components/Show.vue'

// data
import json from './json/data.json'

// exports
export default {
  name: 'app',
  components: {
    Show
  },
  data () {
    return {
      json: json
    }
  }
}

</script>

<style>
.card-section {
  border: none;
}

body {
  margin:2rem;
}

</style>
