<template>
  <div class="randb">
    <!-- Header -->
    <header-comp>
      R&B/Soul
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
  name: "randb",
  data() {
    return {
      artists: [],
      artistDescriptions: [
        {
          name: "H.E.R.",
          description: "Gabriella Sarmiento Wilson, known professionally as H.E.R., is an American singer, songwriter, and musician.",
          born: "June 27, 1997 (age 25 years), Vallejo, CA",
          source: "Wikipedia"
        },
        {
          name: "6LACK",
          description: "Ricardo Valdez Valentine Jr., known professionally as 6lack (pronounced 'black'), is an American singer and rapper. He initially gained notable recognition following the release of his single, \"Prblms\", taken from his debut album, Free 6lack, which was released in November 2016.",
          born: "June 24, 1992 (age 30 years), Baltimore, MD",
          source: "Wikipedia"
        }
      ]
    }
  },
  mounted() {
    // API request to get 6lack info
    const black = {
      method: 'GET',
      url: 'https://spotify23.p.rapidapi.com/search/',
      params: { q: '6lack', type: 'multi', offset: '0', limit: '10', numberOfTopResults: '5' },
      headers: {
        'X-RapidAPI-Key': `${process.env.NUXT_ENV_SPOTIFY_API_KEY}`,
        'X-RapidAPI-Host': 'spotify23.p.rapidapi.com'
      }
    };

    axios.request(black)
      .then(response => ((this.artists).push(response.data)))
      .catch(function (error) {
        console.error(error);
      });

    // API request to get HER info
    const her = {
      method: 'GET',
      url: 'https://spotify23.p.rapidapi.com/search/',
      params: { q: 'h.e.r.', type: 'multi', offset: '0', limit: '10', numberOfTopResults: '5' },
      headers: {
        'X-RapidAPI-Key': `${process.env.NUXT_ENV_SPOTIFY_API_KEY}`,
        'X-RapidAPI-Host': 'spotify23.p.rapidapi.com'
      }
    };

    axios.request(her)
      .then(response => ((this.artists).push(response.data)))
      .catch(function (error) {
        console.error(error);
      });
  },
  components: {
    HeaderComp,
    Accordions
  },
}
</script>