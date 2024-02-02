<script setup lang="ts">
import { appName } from '~/constants'

useHead({
  title: appName,
})

const { refresh } = useAsyncData('test', () => {
  return $fetch('/api/fruit/all', {
  })
})
</script>

<template>
  <button @click="refresh()">
    页面请求
  </button>>
  <VitePwaManifest />
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>

<style>
html,
body,
#__nuxt {
  height: 100vh;
  margin: 0;
  padding: 0;
}

html.dark {
  background: #222;
  color: white;
}
</style>
