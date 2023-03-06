<template>
  <div class="afrobeats">
    <!-- Page header -->
    <header-comp>
      Afrobeats
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
  name: "afrobeats",
  data() {
    return {
      artists: [],
      artistDescriptions: [
        {
          name: "Rema",
          description: "Divine Ikubor, known professionally as Rema, is a Nigerian singer, musician, and rapper. He rose to stardom after releasing the song \"Dumebi\". In 2019, he signed a record deal with Jonzing World, a subsidiary of Mavin Records.",
          born: "May 1, 2000 (age 22 years), Benin City, Nigeria",
          source: "Wikipedia"
        },
        {
          name: "Burna Boy",
          description: "Damini Ebunoluwa Ogulu MFR, known professionally as Burna Boy, is a Nigerian singer, songwriter and record producer. He rose to stardom in 2012 after releasing \"Like to Party\", the lead single from his debut studio album L.I.F.E.",
          born: "July 2, 1991 (age 31 years), Port Harcourt, Nigeria",
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
    // API request to Burna Boy info
    const burnaBoy = {
      method: 'GET',
      url: 'https://spotify23.p.rapidapi.com/search/',
      params: { q: 'burna boy', type: 'multi', offset: '0', limit: '10', numberOfTopResults: '5' },
      headers: {
        'X-RapidAPI-Key': `${process.env.NUXT_ENV_SPOTIFY_API_KEY}`,
        'X-RapidAPI-Host': 'spotify23.p.rapidapi.com'
      }
    };

    axios.request(burnaBoy)
      .then(response => ((this.artists).push(response.data)))
      .catch(error => (console.error(error)));

    // API request to get Rema info
    const rema = {
      method: 'GET',
      url: 'https://spotify23.p.rapidapi.com/search/',
      params: {
        q: 'rema', type: 'multi', offset: '0', limit: '10', numberOfTopResults: '5'
      },
      headers: {
        'X-RapidAPI-Key': `${process.env.NUXT_ENV_SPOTIFY_API_KEY}`,
        'X-RapidAPI-Host': 'spotify23.p.rapidapi.com'
      }
    };

    axios.request(rema)
      .then(response => ((this.artists).push(response.data)))
      .catch(error => (console.error(error)));
  }
}
</script>