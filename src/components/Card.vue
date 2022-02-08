<template>
  <a href="https://www.google.at" class="cursor-pointer">
    <div
      class="grid place-items-center bg-slate-900 py-6 text-white rounded-xl"
    >
      <img src="../assets/logo.png" alt="image" class="w-20" />
      <p class="font-bold">
        {{ title }}
      </p>
      <p
        class="
          text-center
          w-9/12
          pt-2
          block
          overflow-ellipsis
          break-words
          overflow-hidden
          max-h-14
        "
      >
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Rerum nam
      </p>
    </div>
  </a>
</template>

<script>
export default {
  props: ["title"],
};
</script>
