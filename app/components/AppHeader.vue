<script setup lang="ts">
const nuxtApp = useNuxtApp()
const { activeHeadings, updateHeadings } = useScrollspy()

const links = computed(() => [{
  label: 'Home',
  to: '#home',
  icon: 'i-heroicons-cube-transparent',
  active: activeHeadings.value.includes('home')
}])

nuxtApp.hooks.hookOnce('page:finish', () => {
  updateHeadings([
    document.querySelector('#home')
  ])
})
</script>

<template>
  <UHeader>
    <template #logo>
      <UAvatar size="sm" src="https://failfast.blob.core.windows.net/upload/webdetermina/DeterminaLogo.png" />
      Determina
    </template>
  </UHeader>
</template>