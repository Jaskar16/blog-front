<script setup lang="ts">
const items = [
  { label: 'Home', icon: 'pi pi-home', route: '/' },
  { label: 'Cats', icon: 'pi pi-heart', route: '/cats' },
  { label: 'Kittens', icon: 'pi pi-list', route: '/kittens' },
  { label: 'Nuustik', icon: 'pi pi-star', route: '/kittens/nuustik' },
  { label: 'Any cat name', icon: 'pi pi-question', route: '/kittens/anycatnamehere' },
]
</script>
<template>
  <div>
    <Menubar :model="items">
      <template #start>
        <strong style="margin-right: 1rem">Blog</strong>
      </template>
      <template #item="{ item, props }">
        <NuxtLink v-slot="{ href, navigate }" :to="item.route" custom>
          <a :href="href" v-bind="props.action" @click="navigate">
            <span :class="item.icon" />
            <span>{{ item.label }}</span>
          </a>
        </NuxtLink>
      </template>
    </Menubar>

    <NuxtRouteAnnouncer />
    <main style="padding: 1rem">
      <NuxtPage />
    </main>
  </div>
</template>
