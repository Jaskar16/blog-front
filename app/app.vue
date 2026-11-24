<script setup lang="ts">
const route = useRoute()

const items = {
  'Home': '/',
  'Cats': '/cats',
  'Kittens': '/kittens',
  'Nuustik': '/kittens/nuustik',
  'Any cat name': '/kittens/anycatnamehere',
}
</script>
<template>
  <el-container>
    <el-header style="padding: 0">
      <el-menu :default-active="route.path" mode="horizontal" router>
        <el-menu-item v-for="(url, name) in items" :key="url" :index="url">
          {{ name }}
        </el-menu-item>
      </el-menu>
    </el-header>

    <NuxtRouteAnnouncer />
    <el-main>
      <NuxtPage />
    </el-main>
  </el-container>
</template>
