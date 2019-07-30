<template>
  <div class='show'>
  <Summary v-bind:summary='summary'> </Summary>

  <Episodes v-bind:episodes='episodes'></Episodes>
  </div>
</template>

<script>
// components
import Episodes from './Episodes.vue'
import Summary from './Summary.vue'


export default {
  name: 'Show',
  props: ['json'],
  components: {
    Summary,
    Episodes
  },
  data () {
    // format the data into its seperate parts 
    // allowing for the data to be provided to the nessecary components
    const episodes = this.json['_embedded']['episodes']
    const summary = this.json
    delete summary['_embedded']
    return {
      episodes: episodes,
      summary: summary 
    }
  },
}

</script>
