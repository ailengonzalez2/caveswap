<template>
  <ULandingHero
    :ui="{ base: 'text-start', container: 'justify-end h-[80dvh]', wrapper: 'py-0 sm:py-0 md:py-0 relative', links: 'justify-start' }"
    title="Trade crypto and NFTs with confidence" description="Swap, earn, and build tokens and NFT">

    <template #links>
      <div class="flex justify-start w-full">
        <UButton to="/swap" target="_blank" size="xl" icon="i-heroicons-book-open" variant="soft" class="rounded-full">
          Swap
        </UButton>

      </div>

      <!-- <UButton to="https://ui.nuxt.com/pro/components" target="_blank" size="lg" color="red" icon="i-heroicons-cube-transparent" class="bg-transparent">
            Aprender más
          </UButton> -->
    </template>
  </ULandingHero>
</template>
