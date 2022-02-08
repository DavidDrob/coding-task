<template>
  <div class="bg-stone-900 text-white py-4">
    <footer class="w-5/6 m-auto grid grid-cols-3 gap-0">
      <div class="flex items-center">
        <img src="../assets/logo.png" alt="logo" />
      </div>
      <nav class="flex flex-col justify-between">
        <p v-for="(item, index) in navItems" :key="index">
          <a :href="item.link">
            {{ item.name }}
          </a>
        </p>
      </nav>
      <div class="flex flex-col justify-between w-full">
        <FooterItem keyText="Name" value="Lorem Ipsum" />
        <FooterItem keyText="Address" value="Dummy Address 42" />
        <FooterItem keyText="E-Mail" value="lorem@ipsum.com" />
        <FooterItem keyText="Phone" value="+43 123 456 789" />
      </div>
    </footer>
  </div>
</template>

<script>
import FooterItem from "./FooterItem.vue";

export default {
  name: "Footer",
  props: ["navItems"],
  components: {
    FooterItem,
  },
};
</script>
