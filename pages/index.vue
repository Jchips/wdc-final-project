<template>
  <div class="home">
    <section class="hero-image">
      <div id="hero-1" class="hero-text">
        <h1>Music.com</h1>
      </div>
      <div id="hero-2" class="hero-text">
        <h4>A Black artist music page!</h4>
      </div>
    </section>

    <!-- Displays links to music streaming sites. -->
    <section class="links">
      <!-- Spotify -->
      <a href="https://open.spotify.com/genre/frequency-page" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/1/1b/Spotifytranslogo.png" alt="Spotify logo" />
      </a>

      <!-- Apple Music -->
      <a href="https://music.apple.com/us/playlist/the-us-honors-black-music/pl.c1af7ca689e9479f963294904eb1e11e"
        target="_blank">
        <img src="https://cdn.iconscout.com/icon/free/png-256/itunes-28-1100769.png" alt="Apple Music logo" />
      </a>

      <!-- YouTube Music -->
      <a href="https://music.youtube.com/playlist?list=PLyORnIW1xT6xl2LrWGKdr6AtPfedkkmgD" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/d/d8/YouTubeMusic_Logo.png" alt="YouTube Music logo" />
      </a>

      <!-- Deezer -->
      <a href="https://www.deezer.com/us/channels/blackculture" target="_blank">
        <img src="../assets/imgs/deezer-icon.png" alt="Deezer logo" />
      </a>
    </section>

    <section class="home-content">
      <p>This Black history month (Feb. 2023), I wanted to celebrated Black music artists.
        Black people have influenced many of the main genres listened to today.</p>

      <p>The roots of pop, jazz, soul, R&B, hip-hop, gospel, house, folk and disco music can all
        be traced to Black musicians. So many of today's most popular genres, trends and artists
        just wouldn't exist without the work of the most influential Black musicians of the 20th
        century, all of whom helped lay the groundwork for music as we know and love it today.</p>
      <p class="citation">
        “Most Influential Black Musicians: 30 Great Artists Who Changed Music.” <span>Dig!</span>, 6 Oct. 2022,
        https://www.thisisdig.com/feature/most-influential-black-musicians/.
      </p>

      <p>A central pillar of the Black experience has and always will be music. From its roots
        that extend far beyond gospel to modern genre-shaping trendsetters and rulebreakers,
        Black artists have created the music landscape as we know it today. And in honor of
        Black History Month, we want to highlight a handful of the Black artists whose music
        you should celebrate not just this month but every month.</p>
      <p class="citation">
        Maxamillion Polo. “Ones to Watch.” <span>Ones to Watch</span>, 9 Feb. 2022,
        https://www.onestowatch.com/en/blog/black-history-month-artists-2022.
      </p>

      <p>Erykah Badu and Common's song “Love of My Life (An Ode to Hip Hop)” is a beautiful
        analogy of hip-hop music being their first love. I know exactly how they feel because
        music was one of my first loves, too. Both sides of my family are very musically inclined,
        so it's almost like music is ingrained in who I am. Music—particularly Black music—has been
        the soundtrack to my life for as long as I can remember. In my household growing up, each
        activity or mood had a playlist to match—old school hits from the '70s when it was time to
        clean on Saturday mornings, soulful ballads on Sunday evenings when we were getting ready
        for the week ahead, and the hottest, latest records each morning as I got ready for school.
        Music has always been part of me. As I got older, I realized that Black music is more than
        lyrics and melodies; it's actual life-changing, mood altering therapy that I go back to over
        and over again. That's not just the case for me, though. Black music shapes the lives of so
        many people the world over, and it's been that way for centuries. The roots and impact of
        Black music go much deeper than catchy songs and popular artists. For the Black community,
        Black music has always been a messenger, an outlet, and a space of freedom. Let's explore the
        evolution of Black music, starting more than 200 years back, and how Black music is at the hearts
        of all American music, history, and culture. ~ SARAH HUNT-BLACKWELL</p>
      <p class="citation">
        Sarah Hunt-Blackwell. “How Black Music Became America's Soundtrack.” <span>The Everygirl</span>, 25 Feb. 2022,
        https://theeverygirl.com/black-music/.
      </p>
    </section>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  mounted() {
    // Animates the header text on page scroll 
    // Code from: https://css-tricks.com/books/greatest-css-tricks/scroll-animation/ 
    window.addEventListener(
      "scroll",
      () => {
        document.body.style.setProperty(
          "--scroll",
          window.pageYOffset / (document.body.offsetHeight - window.innerHeight)
        );
      },
      false
    );
  }
};
</script>
