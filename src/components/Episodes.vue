<template>
<div class="episodes">
  <b-card class="card-section" title="Seasons">
    <b-button class="mr-2" style="width: 4rem;" variant="outline-primary"
      @click="sortSeason(0)"
      :class="{ active : isActive == 0 }">
      All
    </b-button>
    <b-button variant="outline-primary"
      @click="sortSeason(season)"
      class="mr-2"
      :class="{ active : isActive == season }"
      v-for="season in seasons"
      :key="season">
      {{season}}
    </b-button>
  </b-card>
  <b-card class="card-section">
      <b-card-title>
        <div class="row">
          <div class="input-group">
            <label class="col-auto mb-3">
              Episodes
            </label>
            <select class="sorting" v-model="sortingType">
              <option selected value="date">Date</option>
              <option value="name">Name</option>
            </select>
            <div class="input-group-append sorting">
              <b-button variant="outline-primary" @click="invertSort">
                <font-awesome-icon :icon="sortSymbol"></font-awesome-icon>
              </b-button>
            </div>
          </div>
        </div>
      </b-card-title>
      <div class="row">
        <div class="col-auto mb-3"
          v-for="(episode, index) in sortedEpisodes"
          :key="index">
          <b-card
            class="episode-card"
            :src="episode.url"
          >
            <a :href="episode.url" class="text-decoration-none text-dark">
              <b-card-text name="episode-card" class="row">
                <img :src="episode.image.medium" class="col-md-4 thumbnail rounded-circle">
                <h6 class="col-md-8 centered">{{episode.name}}</h6>
              </b-card-text>
            </a>
            <b-card-text class="small scroll"
                v-html="episode.summary">
            </b-card-text>
            <em class="cardfooter">{{episode.airdate}} | Season: {{episode.season}} | Episode: {{episode.number}}</em>
          </b-card>
        </div>
      </div>
  </b-card>
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
      activeEpisodes: this.episodes,
      sortAsc: true,
      sortSymbol: this.sortAsc ? 'angle-down' : 'angle-up',
      sortingType: 'date'
    }
  },
  computed: {
    sortedEpisodes() {
      var result = this.activeEpisodes;
      let ascDesc = this.sortAsc ? 1 : -1;
      if (this.sortingType === 'date') {
        var sorted = result.sort((a, b) => ascDesc * a.airdate.localeCompare(b.airdate));
      } 
      else {
        var sorted = result.sort((a, b) => ascDesc * a.name.localeCompare(b.name)); 
      } 
      return sorted
    }
  },
  methods: {
    sortSeason: function (season) {
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
    },
    invertSort() {
      this.sortAsc = !this.sortAsc
      this.sortSymbol = !this.sortAsc ? 'angle-down' : 'angle-up'
    }
  }
}
</script>

<style>
.seasons-buttons {
  padding: 2rem;
}
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
    height: 5rem;
    overflow-y: auto;
}

.centered {
  margin: auto;
  padding: 0rem;
}
.cardfooter {
  font-size: 0.7em;
}
.sorting {
  height: 2rem;
  font-size: 0.7em; 
}

/* card hover effect */

.episode-card {
  width: 15rem;
  height: 15rem;
  box-shadow: 0px 2px 4px 0px rgba(0,0,0,0.5);
}
.episode-card:hover {
    box-shadow: 20px 20px 40px 0px rgba(0,0,0,0.5);
  }
</style>
