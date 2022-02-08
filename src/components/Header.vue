<template>
  <div class="bg-stone-900 text-white py-4">
    <header class="w-5/6 m-auto flex items-center justify-between">
      <div class="w-16">
        <img src="../assets/logo.png" alt="logo" />
      </div>
      <nav class="flex w-1/2 md:w-2/6 lg:w-1/6 justify-between">
        <p v-for="(item, index) in navItems" :key="index">
          <a :href="item.link">
            {{ item.name }}
          </a>
        </p>
      </nav>
    </header>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: ["navItems"],
};
</script>
