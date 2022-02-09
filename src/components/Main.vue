<template>
  <div class="text-black py-4 w-5/6 m-auto">
    <input
      type="text"
      class="mb-4 pl-3 text-lg h-10 border border-slate-900 rounded-xl"
      placeholder="search by name"
      v-model="search"
    />
    <main class="grid gap-4 grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
      <Card
        v-for="pokemon in filteredPokemons"
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
      search: "",
    };
  },
  components: {
    Card,
  },
  mounted() {
    // Request first 50 Pokemon's data from the API and push them to the `pokemons` array
    for (let i = 1; i < 50; i++) {
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
  computed: {
    sortedPokemons() {
      return this.pokemons.sort((a, b) => {
        if (a.name < b.name) return -1;
        if (a.name > b.name) return 1;
        return 0;
      });
    },
    filteredPokemons() {
      let newPokemons = [];
      if (this.search.length >= 3) {
        this.sortedPokemons.map((pokemon) => {
          if (pokemon.name.toLowerCase().indexOf(this.search) > -1) {
            newPokemons.push(pokemon);
          }
        });
        return newPokemons;
      }
      return this.sortedPokemons;
    },
  },
};
</script>
