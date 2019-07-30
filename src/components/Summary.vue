<template>
  <div class='summary'>
    <b-container class='summary-container'>
      <b-col>
        <b-img src={{images.medium}} fluid alt={{name}}></b-img>
      </b-col>
    </b-container>
  </div>
</template>

<script>

export default {
  name: 'Summary',
  props: ['summary', 'url', 'name', 'genre', 'rating', 'images']
}
</script>
