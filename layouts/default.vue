<template>
  <!-- navbar links  -->
  <div>
    <nav>
      <NuxtLink to="/">Home</NuxtLink> |
      <nuxt-link to="/LatestView">Latest</nuxt-link> |
      <nuxt-link to="/GridView">Grid</nuxt-link> |
      <nuxt-link to="/PixelsView">Pixels</nuxt-link>
    </nav>
    <nuxt />
  </div>
</template>

<style lang="scss">
@import '../assets/sass/components.content';
@import '../assets/sass/base.normalize';
@import '../assets/sass/settings.responsive';
@import '../assets/sass/styles.scss';

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
  background-color: #343a40; /* Navigation color */
}

nav a.router-link-exact-active {
  color: #fff;
}

</style>
