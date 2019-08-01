<template>
  <div class='summary'>
    <b-card class="card-section">
      <b-media>
        <b-img :src='images.medium'
          slot="aside"
          blank-color="#ccc"
          width="150"
          alt="placeholder">
        </b-img>

        <h3 class="mt-0">
          {{name}}
        </h3>
        <p class="subtitle text-secondary small">
          Genre: {{ genre.join(', ') }} | Rating: {{rating}}
        </p>

        <p v-html="summary">
        </p>

        <a :href="officialSite"
          class="btn btn-outline-primary"
          role="button"
          aria-pressed="true">
          Official Site
        </a>
      </b-media>
    </b-card>
  </div>
</template>

<script>

export default {
  name: 'Summary',
  props: ['summary', 'officialSite', 'name', 'genre', 'rating', 'images']
}
</script>
