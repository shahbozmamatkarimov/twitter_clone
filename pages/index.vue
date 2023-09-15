<template>
  <main class="flex w-full">
    <div
      class="relative flex flex-col items-center justify-start lg:w-full sm:w-7/12 min-h-screen 2xl:ml-[280px] xl:ml-[280px] lg:ml-[80px] sm:ml-[80px]"
    >
      <TwitNav />
      <WhatsHappening />
      <TwitPost />
    </div>
  </main>
</template>

<script setup>
useHead({
  title: "home",
  meta: [{ name: "description", content: "My amazing site." }],
});
</script>
