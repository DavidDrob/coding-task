<template>
  <a :href="link" class="cursor-pointer">
    <div
      class="
        grid
        place-items-center
        bg-slate-900
        h-52
        pb-4
        text-white
        rounded-xl
      "
    >
      <img :src="image" alt="image" class="w-24" />
      <p class="font-bold">
        {{ name }}
      </p>
      <p class="text-center w-7/12 pt-2">
        <!-- Display a comma after every ability or a dot after the last ability -->
        {{ name }}'s abilities are:
        <span v-for="(ability, index) in abilities" :key="index"
          >{{ ability.ability.name
          }}<span v-if="abilities.length - 1 != index">, </span
          ><span v-else>.</span>
        </span>
      </p>
    </div>
  </a>
</template>

<script>
export default {
  props: ["title", "image", "link", "abilities"],
  data() {
    return {
      name: "",
    };
  },
  mounted() {
    // Capitalize the first letter of the name
    this.name = this.title.charAt(0).toUpperCase() + this.title.slice(1);
  },
};
</script>
