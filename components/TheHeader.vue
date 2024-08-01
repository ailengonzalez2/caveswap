<template>
  <UHeader :links="links">
    <template #logo>
      ArgenSwap
    </template>

    <template #right>
      <UColorModeButton />

  
      <w3m-button/>
    </template>
  </UHeader>
</template>



<script setup>
const links = [
  {
    label: "Home",
    to: "/",
    exactHash: true,
  },
  {
    label: "Swap",
    to: "/swap",
  },
];
</script>


