<script setup lang="ts">
import type { NavigationMenuItem } from '@nuxt/ui'

const items: NavigationMenuItem[] = [
  { label: 'Home', to: '/' },
  { label: 'Cats', to: '/cats' },
  { label: 'Kittens', to: '/kittens', exact: true },
  { label: 'Nuustik', to: '/kittens/nuustik' },
  { label: 'Any cat name', to: '/kittens/anycatnamehere' },
]
</script>
<template>
  <UApp>
    <UHeader title="Blog">
      <UNavigationMenu :items="items" />

      <template #right>
        <UColorModeButton />
      </template>

      <template #body>
        <UNavigationMenu :items="items" orientation="vertical" class="-mx-2.5" />
      </template>
    </UHeader>

    <NuxtRouteAnnouncer />
    <UContainer class="py-6">
      <NuxtPage />
    </UContainer>
  </UApp>
</template>
