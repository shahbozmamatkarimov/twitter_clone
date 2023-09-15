<template>
  <div class="container flex mx-auto">
    <TwitLeftSide 
    class="overflow-hidden w-full overflow-y-auto max-h-screen"
    />
    <div
      class="overflow-hidden w-full overflow-y-auto max-h-screen"
    >
      <slot />
    </div>

    <TrendsForYou
      class="overflow-hidden pb-5 overflow-y-auto max-h-screen"
    />
  </div>
</template>

<script setup></script>

<style scoped></style>
