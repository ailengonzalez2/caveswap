<template>
  <UContainer class="pt-20 max-w-lg">
    <h1 class="text-6xl text-center my-5">Swap anytime, anywhere.</h1>
    <UCard :ui="{ background: 'bg-white dark:bg-black' }">
      <!-- <template #header>
        <Placeholder class="h-8" />
      </template> -->

      <div>


        <div class="flex items-end">
          <div class="flex-1">
            <label for="">Vender</label>
            <UInput v-model="sellAmount" type="number" class="w-full rounded-r-none" />
          </div>
          <UButton :label="selectedPayToken.symbol" color="gray" @click="selectPayTokenModal = true" >
            <template #leading>
              <UAvatar :src="`/img/tokens/${selectedPayToken.symbol}.svg`" size="2xs" />
            </template>
          </UButton>


        </div>

        <div>




          <UModal v-model="selectPayTokenModal">
            <div class="p-4">
              <UCard>
                <ul>
                  <li class="token-list-item" v-for="token in tokens" @click="selectPayToken(token)">
                    <img :src="`/img/tokens/${token.symbol}.svg`" alt="">
                    <div>
                      <p>{{ token.symbol }}</p>
                      <p class="text-xs text-gray-400">{{ token.name }}</p>
                    </div>

                  </li>
                </ul>
              </UCard>
            </div>
          </UModal>
        </div>
      </div>

      <div class="flex items-center justify-center gap-3">
        <UFormGroup v-slot="{ error }" label="Comprar">
          <UInput v-model="buyAmount" type="number" />
        </UFormGroup>

        <div>
          <UButton label="Open" @click="isOpen = true" />

          <UModal v-model="isOpen">
            <div class="p-4">
              <Placeholder class="h-48" />
            </div>
          </UModal>
        </div>
      </div>

      <template #footer>
        <UButton block size="lg" variant='soft'>Swap</UButton>
      </template>
    </UCard>
  </UContainer>
</template>

<script setup lang="ts">
const isOpen = ref(false);
const selectPayTokenModal = ref(false);
const tokens = ref([
  {
    name: "Bitcoin",
    symbol: "BTC",
  },
  {
    name: "Ethereum",
    symbol: "ETH",
  },
  {
    name: "Avalanche",
    symbol: "AVAX",
  },
]);

const selectedPayToken = ref({
  name: "Bitcoin",
  symbol: "BTC",
});

const sellAmount = ref("");
const buyAmount = ref("");

function selectPayToken(selectedToken) {
  selectedPayToken.value = selectedToken
  selectPayTokenModal.value = false
  console.log("click", selectedToken.name);
}
</script>

<style>
.token-list-item {
  @apply flex items-center gap-2 mb-4 hover:bg-gray-800
}

.token-list-item img {
  @apply w-8
}
</style>
