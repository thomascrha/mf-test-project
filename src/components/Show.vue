<template>
  <div class='show'>
  <Summary
          :summary='summary.summary'
          :url='summary.url'
          :genre='summary.genres'
          :name='summary.name'
          :rating='summary.rating.average'
          :images='summary.image'>
  </Summary>
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
  }
}

</script>
