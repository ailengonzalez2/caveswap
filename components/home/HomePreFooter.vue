<template>
  <ULandingSection>
    <ULandingCTA :card="false" title="Ready to get started?"
      description="The plataform built for swapping">
      <template #links>
        <UButton to="/swap" size="lg" color="primary" trailing-icon="i-heroicons-arrow-right-20-solid">
          Swap
        </UButton>
      </template>
    </ULandingCTA>
  </ULandingSection>
</template>
