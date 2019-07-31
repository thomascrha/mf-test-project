<template>
 <div class="episodes"> 
  <b-card>
    <b-button-group class="seasons-buttons">
      <b-button variant="outline-primary" class="active">All</b-button>
      <div v-for="season in seasons">
        <b-button variant="outline-primary">
          {{season}}
        </b-button>
      </div>
    </b-button-group>
  </b-card>
  <div class="container-fluid">
    <div class="row">
      <div class="col-auto mb-3" v-for="(episode, index) in episodes">
        <div class="col-auto mb-3">
          <div class="card" style="width: 15rem; height: 15rem;">
              <div class="card-body">
                <h6 class="card-title"><img :src="episode.image.medium" class="thumbnail rounded-circle"></img>{{episode.name}}</h6>
                <p class="card-text small scroll" v-html="episode.summary"></p>
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
