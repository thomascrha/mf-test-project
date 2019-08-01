<template>
 <div class="episodes">
  <b-card>
    <b-button-group class="seasons-buttons">
      <b-button variant="outline-primary"
        @click="sortEpisodes(0)"
        :class="{ active : isActive == 0 }">
        All
      </b-button>
      <b-button variant="outline-primary"
        @click="sortEpisodes(season)"
        :class="{ active : isActive == season }"
        v-for="season in seasons"
        :key="season">
        {{season}}
      </b-button>
    </b-button-group>
  </b-card>
  <div class="container-fluid">
    <div class="row">
      <div class="col-auto mb-3"
        v-for="(episode, index) in activeEpisodes"
        :key="index">
        <div class="col-auto mb-3">
          <div class="card" style="width: 15rem; height: 15rem;">
              <div class="card-body">
                <h6 class="card-title">
                  <img :src="episode.image.medium"
                    class="thumbnail rounded-circle">
                  {{episode.name}}
                </h6>
                <p class="card-text small scroll"
                  v-html="episode.summary"></p>
                <p class="card-footer">akndjsandj</p>
              </div>
          </div>
      </div>
    </div>
  </div>
</div>
</div>
</template>

<script>

export default {
  name: 'Episodes',
  props: ['episodes', 'seasons'],
  data () {
    return {
      isActive: 0,
      // set the default to all episodes
      activeEpisodes: this.episodes
    }
  },
  methods: {
    sortEpisodes: function (season) {
      // set the element to active
      this.isActive = season
      // create empty list for season episodes
      var seasonEpisodes = []

      // check if all is selected
      if (season === 0) {
        this.activeEpisodes = this.episodes
      } else {
        // filter the episodes
        for (const episode of this.episodes) {
          if (episode.season === season) {
            seasonEpisodes.push(episode)
          }
        }
        this.activeEpisodes = seasonEpisodes
      }
    }
  }
}
</script>

<style>
.thumbnail {
  position: relative;
  width: 5rem;
  height: 5rem;
  padding: 0.5rem;
  overflow: hidden;
}
.thumbnail img {
  position: absolute;
  left: 50%;
  top: 50%;
  -webkit-transform: translate(-50%,-50%);
      -ms-transform: translate(-50%,-50%);
          transform: translate(-50%,-50%);
}
.scroll {
    max-height: 4rem;
    overflow-y: auto;
}

</style>
