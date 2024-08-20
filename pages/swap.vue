<template>
  <UContainer class="pt-20 max-w-lg">
    <h1 class="text-6xl text-center my-5">Swap anytime, anywhere.</h1>
    <UCard :ui="{ background: 'bg-white dark:bg-[#1f1f1f]', ring: 'ring-0 ring-gray-200 dark:ring-none', }">
      <!-- <template #header>
        <Placeholder class="h-8" />
      </template> -->

      <div>


        <div class="flex items-end">
          <div class="flex-1">
            <label for="">Sell</label>
            <UInput :ui="{
      color: {
        white: {
          outline: 'ring-gray-300 dark:ring-transparent dark:bg-[#1f1f1f] dark:text-white',
        },
      },
    }" v-model="sellAmount" type="number" class="w-full " size="xl" placeholder="0" />
          </div>
          <UButton :label="selectedPayToken.symbol" color="white" variant="ghost" icon="i-heroicons-x-mark-20-solid"
            @click="selectPayTokenModal = true" size="xl" :ui="{
      color: {
        white: {
          ghost: ' hover:bg-white dark:hover:bg-black',
        },
      },
    }">
            <template #leading>
              <UAvatar :src="`/img/tokens/${selectedPayToken.symbol}.svg`" size="2xs" />
            </template>

            <template #trailing>
              <UIcon name="i-heroicons-chevron-down-20-solid" class="w-5 h-5" />
            </template>
          </UButton>


        </div>

        <div>
          <UModal v-model="selectPayTokenModal" :ui="{
      overlay: {

        transition: {
          enter: 'ease-in-out duration-300',
        },
      }
    }">
            <div class="p-4">
              <UCard>
                <ul>
                  <li class="token-list-item" v-for=" token  in  tokens " @click="selectPayToken(token)">
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

      <div class="flex justify-center pt-4">
        <UButton @click="swapTokensPositions" :ui="{ rounded: 'rounded-full' }" icon="i-heroicons-arrows-up-down"
          size="xl" color="primary" square />
      </div>

      <div>

        <div class="flex items-end">
          <div class="flex-1">
            <label for="">Buy</label>
            <UInput :ui="{
      color: {
        white: {
          outline: 'ring-gray-300 dark:ring-transparent dark:bg-[#1f1f1f] dark:text-white',
        },
      },
    }" v-model="buyAmount" type="number" class="w-full rounded-r-none" size="xl" placeholder="0" />
          </div>
          <UButton :label="selectedSellToken.symbol" color="white" variant="ghost" @click="selectSellTokenModal = true"
            size="xl" :ui="{
      color: {
        white: {
          ghost: ' hover:bg-white dark:hover:bg-black',
        },
      },
    }
      ">
            <template #leading>
              <UAvatar :src="`/img/tokens/${selectedSellToken.symbol}.svg`" size="2xs" />
            </template>
            <template #trailing>
              <UIcon name="i-heroicons-chevron-down-20-solid" class="w-5 h-5" />
            </template>
          </UButton>


        </div>

        <div>
          <UModal v-model="selectSellTokenModal">
            <div class="p-4">
              <UCard>
                <ul>
                  <li class="token-list-item" v-for=" token  in  tokens " @click="selectSellToken(token)">
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

      <template #footer>
        <UButton block size="lg">Swap</UButton>
      </template>
    </UCard>
  </UContainer>
</template>

<script setup lang="ts">
const isOpen = ref(false);
const selectPayTokenModal = ref(false);
const selectSellTokenModal = ref(false);
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

const selectedSellToken = ref({
  name: "Ethereum",
  symbol: "ETH",
});

const sellAmount = ref("");
const buyAmount = ref("");

function selectPayToken(selectedToken) {
  selectedPayToken.value = selectedToken
  selectPayTokenModal.value = false
  console.log("click", selectedToken.name);
}

function selectSellToken(selectedToken) {
  selectedSellToken.value = selectedToken
  selectSellTokenModal.value = false
  console.log("click", selectedToken.name);
}

function swapTokensPositions() {
  const oldPayToken = selectedPayToken.value
  const oldSellToken = selectedSellToken.value

  selectedPayToken.value = oldSellToken
  selectedSellToken.value = oldPayToken
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
