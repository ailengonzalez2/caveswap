<template>
  <ULandingSection id="features" title="Swap Your Tokens, Simplified">
    <template #description>
      Effortlessly exchange your digital assets with our user-friendly platform. Fast, secure, and designed for all your blockchain needs.
    </template>

    <UPageGrid>
      <UPageCard :ui="{ background: 'bg-gray-50 dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }" class="col-span-2" icon="i-heroicons-wrench-screwdriver" title="User-Friendly Interface"
        description="Navigate through our intuitive and modern design, making complex blockchain interactions simple for everyone." />
      <UPageCard :ui="{ background: 'bg-gray-50 dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }" class="col-span-1" icon="i-heroicons-square-3-stack-3d" title="Seamless Token Swapping"
        description="Effortlessly exchange your tokens with just a few clicks, ensuring a smooth and hassle-free experience." />
    </UPageGrid>

    <UPageGrid>
      <UPageCard :ui="{ background: 'bg-gray-50 dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }" icon="i-heroicons-wrench-screwdriver" title="Secure Transactions"
        description="Experience lightning-fast swaps with consistent performance, so you never miss an opportunity." />
      <UPageCard :ui="{ background: 'bg-gray-50 dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }" icon="i-heroicons-square-3-stack-3d" title="Fast and Reliable"
        description="Provide liquidity to pools on Uniswap and earn fees on swaps." />
      <UPageCard :ui="{ background: 'bg-gray-50 dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }" icon="i-heroicons-device-phone-mobile" title="Comprehensive Support"
        description="Get help when you need it with our dedicated support team, ready to assist you 24/7." />
    </UPageGrid>
  </ULandingSection>
</template>
