<template>
  <ULandingSection id="features" title="The freedom to build anything">
    <template #description>
      Nuxt UI Pro ships with an extensive set of advanced components that cover a wide range of use-cases.<br> Carefully
      crafted to reduce boilerplate code without sacrificing flexibility.
    </template>

    <UPageGrid>
      <UPageCard :ui="{ background: 'bg-white dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }" class="col-span-2 bg-red-100" icon="i-heroicons-wrench-screwdriver" title="Swap tokens"
        description="Buy, sell, and explore tokens on Ethereum, Polygon, Optimism, and more." />
      <UPageCard :ui="{ background: 'bg-white dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }" class="col-span-1" icon="i-heroicons-square-3-stack-3d" title="Trade NFTs"
        description="Buy and sell NFTs across marketplaces to find more listings at better prices." />
    </UPageGrid>

    <UPageGrid>
      <UPageCard :ui="{ background: 'bg-white dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }" icon="i-heroicons-wrench-screwdriver" title="Buy crypto"
        description="Buy crypto with your credit card or bank account at the best rates." />
      <UPageCard :ui="{ background: 'bg-white dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }" icon="i-heroicons-square-3-stack-3d" title="Earn"
        description="Provide liquidity to pools on Uniswap and earn fees on swaps." />
      <UPageCard :ui="{ background: 'bg-white dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }" icon="i-heroicons-device-phone-mobile" title="Build dApps"
        description=" Build apps and tools on the largest DeFi protocol on Ethereum." />
    </UPageGrid>
  </ULandingSection>
</template>
