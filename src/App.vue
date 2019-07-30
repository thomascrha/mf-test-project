<template>
  <div id="app">
  <Show v-bind:json='json'> </Show>
  </div>
</template>

<script>
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
