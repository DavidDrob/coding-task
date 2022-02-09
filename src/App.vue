<template>
  <Header :navItems="links" />
  <Main />
  <Footer :navItems="links" />
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";

export default {
  components: {
    Header,
    Main,
    Footer,
  },
  data() {
    return {
      links: [
        {
          name: "API",
          link: "https://pokeapi.co/",
        },
        {
          name: "Games",
          link: "https://www.pokemon.com/us/pokemon-video-games/",
        },
        {
          name: "Collectibles",
          link: "https://www.amazon.com/Pokemon-Collectibles/s?k=Pokemon+Collectibles",
        },
      ],
    };
  },
};
</script>