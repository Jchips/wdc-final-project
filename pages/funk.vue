<template>
  <div class="funk">
    <!-- Page header -->
    <header-comp>
      Funk
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
  name: "funk",
  data() {
    return {
      artists: [],
      artistDescriptions: [
        {
          name: "James Brown",
          description: "James Joseph Brown (May 3, 1933 - December 25, 2006) was an American singer, record producer, bandleader and actor. The central progenitor of funk music and a major figure of the 20th century, he is referred to by various honorific nicknames, some of which include \"the Hardest Working Man in Show Business\", \"Godfather of Soul\", \"Mr. Dynamite\", and \"Soul Brother No. 1\". In a career that lasted more than 50 years, he influenced the development of several music genres.",
          born: "May 3, 1933, Atlanta, GA",
          source: "Wikipedia"
        },
        {
          name: "Earth, Wind & Fire",
          description: "Earth, Wind & Fire is an American band whose music spans the genres of jazz, R&B, soul, funk, disco, pop, Latin, and Afro pop. They are among the best-selling bands of all time, with sales of over 90 million records worldwide. The band was founded in Chicago by Maurice White in 1969, growing out of the Salty Peppers.",
          born: "1969",
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
    // API request to get James Brown info
    const jamesBrown = {
      method: 'GET',
      url: 'https://spotify23.p.rapidapi.com/search/',
      params: { q: 'james brown', type: 'multi', offset: '0', limit: '10', numberOfTopResults: '5' },
      headers: {
        'X-RapidAPI-Key': `${process.env.NUXT_ENV_SPOTIFY_API_KEY}`,
        'X-RapidAPI-Host': 'spotify23.p.rapidapi.com'
      }
    };

    axios.request(jamesBrown)
      .then(response => ((this.artists).push(response.data)))
      .catch(error => (console.error(error)));

    // API request to get Earth, Wind & Fire info
    const earthWindFire = {
      method: 'GET',
      url: 'https://spotify23.p.rapidapi.com/search/',
      params: {
        q: 'earth, wind & fire',
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

    axios.request(earthWindFire)
      .then(response => ((this.artists).push(response.data)))
      .catch(error => (console.error(error)));
  }
}
</script>