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
          name: "Vue",
          link: "https://vuejs.org/",
        },
        {
          name: "Vite",
          link: "https://vitejs.dev/",
        },
        {
          name: "Tailwind",
          link: "https://tailwindcss.com/",
        },
      ],
    };
  },
};
</script>