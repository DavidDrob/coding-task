<template>
  <div class="bg-stone-900 text-white py-4">
    <footer class="w-5/6 m-auto grid grid-cols-3 grid-rows-1 gap-0">
      <div><img src="../assets/logo.png" alt="logo" /></div>
      <nav class="flex flex-col justify-between">
        <p v-for="(item, index) in navItems" :key="index">
          <a :href="item.link">
            {{ item.name }}
          </a>
        </p>
      </nav>
      <div class="w-1/2 flex flex-col justify-between">
        <div class="flex justify-between py-2">
          <p>Name</p>
          <p>Lorem Ipsum</p>
        </div>
        <div class="flex justify-between py-2">
          <p>Address</p>
          <p>dummy address 42</p>
        </div>
        <div class="flex justify-between py-2">
          <p>E-Mail</p>
          <p>lorem@ipsum.com</p>
        </div>
        <div class="flex justify-between py-2">
          <p>Phone</p>
          <p>+43 123 456 789</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: "Footer",
  props: ["navItems"],
};
</script>
