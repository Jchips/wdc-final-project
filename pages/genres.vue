<template>
  <div class="genres">
    <!-- Header -->
    <header-comp>Genres</header-comp>
    
    <!-- Makes a card for each different image using v-for loop with an array -->
    <genre-card :images="images" :learnMore="learnMore" :alts="alts" :imageTitle="imageTitle" :genre="genre"
      :genreDescription="genreDescription" :descriptionCreds="descriptionCreds">
    </genre-card>
  </div>
</template>

<script>
import HeaderComp from "@/components/HeaderComp.vue";
import GenreCard from "@/components/GenreCard.vue";

export default {
  name: 'genres',
  data() {
    return {
      learnMore: ["https://www.loc.gov/collections/songs-of-america/articles-and-essays/musical-styles/popular-songs-of-the-day/rhythm-and-blues/",
        "https://www.masterclass.com/articles/hip-hop-guide",
        "https://www.rollingstone.com/music/music-features/afrobeats-global-rise-1282575/",
        "https://mn2s.com/news/features/funk-foundations/"],
      images: ["https://live.staticflickr.com/65535/32749439287_d7a3845b2e_b.jpg",
        "https://live.staticflickr.com/5459/9684962925_1df4d9f544_b.jpg",
        "https://i.ytimg.com/vi/RApT1oyitR8/maxresdefault.jpg",
        "https://media.snl.no/media/201151/article_topimage_funk.jpeg"],
      alts: ["American R&B/soul musician Stevie Wonder performing", "Popular rapper Nas onstage at the Les Ardentes Festival-2417",
        "Afrobeats artists Burna Boy and Wizkid", "Earth, Wind & Fire performing"],
      imageTitle: ["American R&B/soul musician Stevie Wonder", "Popular rapper Nas", "Burna Boy and Wizkid", "Earth, Wind & Fire"],
      genre: ["R&B/Soul", "Hip-Hop/Rap", "Afrobeats", "Funk"],
      genreDescription: ["Historically speaking, though, \"rhythm and blues\" as we understand it today most often describes a style of music that developed after World War II that combines elements of pop, gospel, blues and jazz with a strong back beat. The African American styles that emerged in those years were often played by small groups that emphasized rhythmic drive over the instrumental and harmonic complexity of the swing orchestras. Their vocalists often sang in an uninhibited and emotionally direct style. In major cities, teenaged vocal groups with little or no instrumental accompaniment were a growing presence. They took their inspiration from both gospel singers and successful African American pop stylists such as the Ink Spots. The term \"doo-wop\" is well known now, but it was not applied to these groups until much later, and it refers to the vocables and nonsense syllables these group sang to compensate for their lack of instruments. All of these styles were significant to the development of rock and roll a few years later.",
        "Hip-hop is a genre of music most often characterized by a strong, rhythmic beat and a rapping vocal track. The genre originated in New York City in the 1970s as a cultural exchange among Black, Latino, and Caribbean youth and has grown into one of the most consumed genres of music in the United States. As a culture, hip-hop is built on four main pillars: DJing, rapping (also called MCing), breakdancing (usually called breaking or b-boying), and graffiti. Since its inception, hip-hop has birthed dozens of subgenres, including trap, grime, gangsta rap, rap rock (or nu metal), crunk, chillhop, bounce, mumble rap, Latin hip-hop, and conscious hip-hop.",
        "In 2006, a crew of young musicians from Nigeria set up the Hottest Coalition of Nigerian DJs. The group comprised artists living in the country as well as in the growing diaspora around the world. Their mission was to promote the kind of music that was popular in West Africa at the time, by acts like P-Square, 2Baba, and D'banj. These were tunes with elements of electronic and dance music set to African percussion, as well as including hints of highlife, dancehall, hip-hop, and R&B — origins traceable across the spectrum of Black expression. “It was obvious that [Africans living abroad] were craving their own [music], because that's one of the ways they could connect back home,” says DJ Neptune, one of the earliest members of the coalition. “This was before we started having blogs coming into the game,” he says. Over the years, the kind of music they were promoting has become known as Afrobeats, a term that describes the most popular music coming out of West Africa. Coined in the aughts, Afrobeats (with an “S”) is similar in name to the Afrobeat music popularized by Fela Kuti in the 1970s but is distinct in its more modern origin and flavor. While Kuti's music was characteristically political and orchestral, Afrobeats is often jovial, digitally produced, and sung in English, West African, and pidgin languages.",
        "Funk is a musical genre that developed in the United States by African-American musicians in the 1960s. Funk was born from the influence of many genres: jazz, R&B, soul, and African grooves. Over the decades it has influenced jazz, R&B and soul music in return, and it gave birth to the entire genre of hip-hop. But despite its multiple points of origin, funk is often traced back to the work of one man. James Brown is known as the godfather of funk."],
      descriptionCreds: ["The Library of Congress", "MasterClass", "RollingStone",
        "MN2S and Hakkens, Chris, et al. “Funk.” Store Norske Leksikon, https://snl.no/funk."],
      title: 'Genre'
    }
  },
  head() {
    return {
      title: this.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Information on the origination of the popular music genres: hip-hop/rap, R&B/soul, afrobeats and funk.'
        }
      ]
    }
  },
  components: {
    GenreCard,
    HeaderComp,
  },
}
</script>