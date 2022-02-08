<template>
  <div class="text-black py-4">
    <main
      class="w-5/6 m-auto grid gap-4 grid-cols-1 md:grid-cols-2 lg:grid-cols-3"
    >
      <Card
        v-for="pokemon in pokemons"
        :key="pokemon.id"
        :title="pokemon.name"
        :image="pokemon.image"
        :link="pokemon.link"
        :abilities="pokemon.abilities"
      />
    </main>
  </div>
</template>

<script>
import Card from "./Card.vue";
import axios from "axios";

export default {
  name: "Main",
  data() {
    return {
      pokemons: [],
    };
  },
  components: {
    Card,
  },
  mounted() {
    // Request first 22 Pokemon's data and push them to the `pokemons` array
    for (let i = 1; i < 22; i++) {
      axios.get(`https://pokeapi.co/api/v2/pokemon/${i}`).then((r) => {
        const id = r.data.id;
        const name = r.data.name;
        const image = r.data.sprites.front_default;
        const abilities = r.data.abilities;
        const link = "https://www.google.at/search?q=" + r.data.name;

        this.pokemons.push({
          id,
          name,
          image,
          abilities,
          link,
        });
      });
    }
  },
};
</script>
