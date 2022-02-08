<template>
  <div class="text-black py-4">
    <main
      class="w-5/6 m-auto grid gap-4 grid-cols-1 md:grid-cols-2 lg:grid-cols-3"
    >
      <Card title="1" />
      <Card title="2" />
      <Card title="3" />
    </main>
  </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "Main",
  components: {
    Card,
  },
};
</script>
