<template>
  <div class='summary'>
    <b-card>
      <b-media>
        <b-img :src='images.medium' slot="aside" blank-color="#ccc" width="150" alt="placeholder"></b-img>

        <h4 class="mt-0">
          {{name}}
        </h4>
        <span class="text-sm">
          Genre: {{ genre.join(', ') }} | Rating: {{rating}}
        </span>

        <p v-html="summary">
        </p>

        <a :href="url" class="btn btn-outline-primary" role="button" aria-pressed="true">Official Site</a>
      </b-media>
    </b-card>
  </div>
</template>

<script>

export default {
  name: 'Summary',
  props: ['summary', 'url', 'name', 'genre', 'rating', 'images']
}
</script>
