<template>
  <ULandingSection>
    <ULandingCTA class="border-green-500" title="Ready to get started?"
      description="The plataform built for swapping">
      <template #links>
        <!-- <UButton to="https://ui.nuxt.com/pro/purchase" target="_blank" size="lg" color="black" icon="i-heroicons-credit-card">
              Buy now
            </UButton> -->
        <UButton to="/swap" size="lg" color="primary" trailing-icon="i-heroicons-arrow-right-20-solid">
          Swap
        </UButton>
      </template>
    </ULandingCTA>
  </ULandingSection>
</template>
