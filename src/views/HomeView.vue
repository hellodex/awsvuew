
<template>
  <h1>VITE_API_URL:{{ WEB_URL }}</h1>

  
  <WalletConnect v-if="!isConnected" />
  <WalletDisconnected v-if="isConnected"/>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import WalletConnect from '@/components/WalletConnect.vue'
import WalletDisconnected from '@/components/WalletDisconnected.vue'
import { useGlobalStore } from '@/stores/global'

const globalStore = useGlobalStore()
const WEB_URL = import.meta.env.VITE_API_URL
console.log('VITE_TG_URL:',import.meta.env.VITE_TG_URL)


const isConnected = computed(() => globalStore.walletInfo.isConnected)
</script>

