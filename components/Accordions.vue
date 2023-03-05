<template>
  <div class="accordions">
    <!-- Creates accordion for each artist using v-for loop with an array of objects -->
    <div class="accordion">
      <div v-for="(artist, index) in artists" v-bind:key="index" class="accordion-item">
        <div class="accordion-header" :id="`header${index}`">
          <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse"
            :data-bs-target="`#accordion-${artist.users.items[0].data.id}`" aria-expanded="false"
            aria-controls="collapseOne">
            {{ artist.artists.items[0].data.profile.name }}
          </button>
        </div>
        <!-- Accordion body -->
        <div :id="`accordion-${artist.users.items[0].data.id}`" class="accordion-collapse collapse"
          :aria-labelledby="`header${index}`">
          <div class="accordion-body">
            <!-- Creates a grid inside the accordion with an image on the left and carousel on the right -->
            <div class="row">
              <div class="col-xl-4 col-lg-4 col-md-4 col-sm-3 col-12 img-container">
                <img :src="artist.artists.items[0].data.visuals.avatarImage.sources[0].url" class="img img-fluid"
                  :alt="`image of ${artist.artists.items[0].data.profile.name}`">
              </div>
              <div class="col-xl-8 col-lg-8 col-md-8 col-sm-9 col-12">
                <!-- Adds carousel -->
                <div :id="`artist-${artist.users.items[0].data.id}`" class="carousel slide" data-bs-interval="false"
                  data-ride="carousel">
                  <div class="carousel-inner">
                    <div class="carousel-item active">
                      <h2>{{ artist.artists.items[0].data.profile.name }}</h2>
                      <!-- Loops thru each artist description to figure out which one to use bc the API requests come in random orders. -->
                      <!-- If the artist is the same one as the object in the artistDescrption array, then paste their information -->
                      <div v-for="artistDescription in artistDescriptions" :key="artistDescription">
                        <div v-if="artist.artists.items[0].data.profile.name === artistDescription.name">
                          <p>{{ artistDescription.description }}</p><br>
                          <p>Born: {{ artistDescription.born }}</p><br>
                          <p>Description source: {{ artistDescription.source }}</p>
                        </div>
                      </div>
                      <a :href="artist.artists.items[0].data.uri" class="btn btn-success" target="_blank">Go to Spotify
                        profile</a>
                    </div>
                    <!-- Loops thru 10 of the artist's popular tracks and makes page for each of them-->
                    <div v-for="track in artist.tracks.items" :key="index" class="carousel-item">
                      <h2>{{ artist.artists.items[0].data.profile.name }}</h2>
                      <h3>Popular tracks</h3>
                      <h5>Track: {{ track.data.name }}</h5>
                      <img :src="track.data.albumOfTrack.coverArt.sources[0].url" :alt="`${track.data.name} track`">
                      <p>Album name: {{ track.data.albumOfTrack.name }}</p>
                      <p>Content rating: {{ track.data.contentRating.label }}</p>
                    </div>
                  </div>
                  <!-- Left and right controls-->
                  <button class="carousel-control-prev" type="button"
                    :data-bs-target="`#artist-${artist.users.items[0].data.id}`" data-bs-slide="prev">
                    <span class="carousel-control-prev-icon"></span>
                  </button>
                  <button class="carousel-control-next" type="button"
                    :data-bs-target="`#artist-${artist.users.items[0].data.id}`" data-bs-slide="next">
                    <span class="carousel-control-next-icon"></span>
                  </button>
                </div>
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
  props: {
    artists: {
      type: Array
    },

    artistDescriptions: {
      type: Array
    }
  },
}
</script>