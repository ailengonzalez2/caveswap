<script setup>
  import { createWeb3Modal, defaultWagmiConfig } from '@web3modal/wagmi/vue'
  import { mainnet, arbitrum } from 'viem/chains'

  // 1. Get projectId at https://cloud.walletconnect.com
  const projectId = '213ebc649b343df24487a8ab4a0cdf5d'

  // 2. Create wagmiConfig
  const metadata = {
    name: 'Web3Modal',
    description: 'Web3Modal Example',
    url: 'https://web3modal.com',
    icons: ['https://avatars.githubusercontent.com/u/37784886']
  }

  const chains = [mainnet, arbitrum]
  const wagmiConfig = defaultWagmiConfig({ chains, projectId, metadata })

  // 3. Create modal
  createWeb3Modal({ wagmiConfig, projectId, chains, themeVariables: {
    '--w3m-accent': '#6366f1',
  } })
  

useHead({
  title: 'Nuxt UI Pro - Starter',
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ],
  link: [
    { rel: 'icon', href: '/favicon.ico' }
  ],
  htmlAttrs: {
    lang: 'en'
  }
})

useSeoMeta({
  description: 'Nuxt UI Pro is a collection of premium components built on top of Nuxt UI to create beautiful & responsive Nuxt applications in minutes.'
})
</script>

<template>
  <TheHeader/>

  <UMain>
    <NuxtPage />
  </UMain>

  <TheFooter />
</template>
