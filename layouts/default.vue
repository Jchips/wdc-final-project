<template>
  <!-- navbar links  -->
  <div>
    <nav>
      <NuxtLink to="/">Home</NuxtLink> |
      <nuxt-link to="/genres">About Genres</nuxt-link> |
      <nuxt-link to="/randb">R&B/Soul</nuxt-link> |
      <nuxt-link to="/hiphop">Hip-Hop/Rap</nuxt-link> |
      <nuxt-link to="/afrobeats">Afrobeats</nuxt-link> |
      <nuxt-link to="/funk">Funk</nuxt-link>
    </nav>
    <nuxt />
  </div>
</template>

<style lang="scss">
@import '../assets/sass/components.content';
@import '../assets/sass/base.normalize';
@import '../assets/sass/settings.responsive';
@import '../assets/sass/styles.scss';

</style>
