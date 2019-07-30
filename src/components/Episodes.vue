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
    <b-card-group deck>
      <b-card 
        no-body 
        class="b1" 
      >
        <b-row no-gutters>
          <b-col md="6">
            <b-card-img src="https://picsum.photos/400/400/?image=20" 
              class="rounded-circle"></b-card-img
            >
          </b-col>
          <b-col md="6">
            <b-card-body title="Horizontal Card">
              <b-card-text>
                This is a wider card with supporting text as a natural lead-in to additional content.
                This content is a little bit longer.
              </b-card-text>
            </b-card-body>
          </b-col>
        </b-row>
      </b-card>
      <b-card 
        no-body 
        class="m1" 
      >
        <b-row no-gutters>
          <b-col md="6">
            <b-card-img src="https://picsum.photos/400/400/?image=20" 
              class="rounded-circle"></b-card-img
            >
          </b-col>
          <b-col md="6">
            <b-card-body title="Horizontal Card">
              <b-card-text>
                This is a wider card with supporting text as a natural lead-in to additional content.
                This content is a little bit longer.
              </b-card-text>
            </b-card-body>
          </b-col>
        </b-row>
      </b-card>
    </b-card-group>
  </div>
 </div>
</template>

<script>
export default {
  name: 'Episodes',
  props: ['episodes', 'seasons']
}
</script>

<style>

@media(max-width: 768px){
      .card-deck .card{
        flex: 0 0 45%;
        margin: 20px auto;
      }
    }

@media(max-width: 619px){
	.card-deck .card{
		width: 80%;
	}

}
</style>
