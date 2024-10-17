<template>
  <UHeader :links="links">
    <template #logo>
      CaveSwap
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

<style>
button[data-size='md'] > wui-text {
  color: red !important;
  --local-color: red!important;
}

</style>


