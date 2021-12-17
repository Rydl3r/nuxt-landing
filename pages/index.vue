<template>
  <div class="text-center py-16">
    <h1 class="font-light text-6xl pb-10">Welcome!</h1>
    <h2 class="text-2xl pb-10">
      At <span>Boring Company</span> we value our clients the most.
    </h2>
    <h3 class="pb-10 text-xl">Learn more about our philosophy and culture</h3>
    <NuxtLink
      to="/about"
      class="
        bg-blue-500
        hover:bg-blue-700
        text-white
        font-bold
        py-2
        px-4
        rounded
        transition
      "
    >
      Learn More
    </NuxtLink>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>
