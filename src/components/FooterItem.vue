<template>
  <div>
    <div class="flex flex-col md:flex-row md:justify-between py-2">
      <p>{{ keyText }}</p>
      <p>{{ value }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer Item right",
  props: ["keyText", "value"],
};
</script>

<style lang="scss" scoped>
</style>