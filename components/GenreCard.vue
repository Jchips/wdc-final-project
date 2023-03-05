<template>
  <div class="cards">
    <!-- Makes a card for each different image using v-for loop with an array -->
    <div v-for="(image, index) in images" :key="index" class="genre">
      <img :src="image" class="img-fluid genre-img" :alt="alts[index]" :title="imageTitle[index]">
      <div class="card text-center">
        <div class="card-header">
          {{ genre[index] }}
        </div>
        <div class="card-body">
          <p class="card-text">{{ genreDescription[index] }}</p>
          <a v-bind:href="learnMore[index]" class="btn btn-primary" target="_blank">Learn more</a>
        </div>
        <div class="card-footer text-muted">
          Text source: {{ descriptionCreds[index] }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GenreCard',
  props: {
    images: {
      type: Array
    },
    learnMore: {
      type: Array
    },
    alts: {
      type: Array
    },
    imageTitle: {
      type: Array
    },
    genre: {
      type: Array
    },
    genreDescription: {
      type: Array
    },
    descriptionCreds: {
      type: Array
    }
  }
}
</script>