<template>
  <div class="hiphop">
    <!-- Page header -->
    <header-comp>
      Hip-Hop/Rap
    </header-comp>

    <!-- Creates accordion for each artist using v-for loop with an array of objects -->
    <Accordions :artists="artists" :artistDescriptions="artistDescriptions"></Accordions>
  </div>
</template>

<script>
import HeaderComp from "@/components/HeaderComp.vue";
import Accordions from "../components/Accordions.vue";
import axios from 'axios'
export default {
  name: "hiphop",
  data() {
    return {
      artists: [],
      artistDescriptions: [
        {
          name: "Kendrick Lamar",
          description: "Kendrick Lamar Duckworth is an American rapper and songwriter. Known for his progressive musical styles and socially conscious songwriting, he is often considered one of the most influential hip hop artists of his generation.",
          born: "June 17, 1987 (age 35 years), Compton, CA",
          source: "Wikipedia"
        },
        {
          name: "J. Cole",
          description: "Jermaine Lamarr Cole is an American rapper and record producer. Born on a military base in Germany and raised in Fayetteville, North Carolina, Cole initially gained recognition as a rapper following the release of his debut mixtape, The Come Up, in early 2007.",
          born: "January 28, 1985 (age 38 years), Frankfurt, Germany",
          source: "Wikipedia"
        }
      ]
    }
  },
  components: {
    HeaderComp,
    Accordions
  },
  mounted() {
    // API request to get J. Cole info
    const jcole = {
      method: 'GET',
      url: 'https://spotify23.p.rapidapi.com/search/',
      params: { q: 'j. cole', type: 'multi', offset: '0', limit: '10', numberOfTopResults: '5' },
      headers: {
        'X-RapidAPI-Key': `${process.env.NUXT_ENV_SPOTIFY_API_KEY}`,
        'X-RapidAPI-Host': 'spotify23.p.rapidapi.com'
      }
    };

    axios.request(jcole)
      .then(response => ((this.artists).push(response.data)))
      .catch(error => (console.error(error)));

    // API request to get Kendrick Lamar info
    const kendrickLamar = {
      method: 'GET',
      url: 'https://spotify23.p.rapidapi.com/search/',
      params: {
        q: 'kendrick lamar',
        type: 'multi',
        offset: '0',
        limit: '10',
        numberOfTopResults: '5'
      },
      headers: {
        'X-RapidAPI-Key': `${process.env.NUXT_ENV_SPOTIFY_API_KEY}`,
        'X-RapidAPI-Host': 'spotify23.p.rapidapi.com'
      }
    };

    axios.request(kendrickLamar)
      .then(response => ((this.artists).push(response.data)))
      .catch(error => (console.error(error)));
  }
}
</script>