<template>
  <div>
    <UPage>
      <UPageBody :ui="{ wrapper: 'mt-0 pb-0' }">
        <ULandingSection :ui="{ container: 'w-full lg:h-[400px]' }"
          class="bg-repeat-round  bg-[url('https://failfast.blob.core.windows.net/upload/webdetermina/DeterminawebBG.png')]"
          title="Determina">
          <template #headline>
            <img src="https://failfast.blob.core.windows.net/upload/webdetermina/DeterminaLogo.png"
              class="mx-auto w-40 h-40 -mt-8" />
          </template>
        </ULandingSection>

        <ULandingSection title="Financial technology service provider"
          class="  bg-[url('https://failfast.blob.core.windows.net/upload/webdetermina/Worldbg.png')]">
          <UPageGrid :ui="{ wrapper: 'grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-2 gap-8' }" id="home"
            class="scroll-mt-[calc(var(--header-height)+140px+128px+96px)]">
            <ULandingCard v-for="(item, index) in itemFeature" :key="index" v-bind="item" target="_blank" />
          </UPageGrid>
        </ULandingSection>

      </UPageBody>
    </UPage>
  </div>
</template>

<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())

useSeoMeta({
  title: page.value.title,
  ogTitle: page.value.title,
  description: page.value.description,
  ogDescription: page.value.description
})

const itemFeature = ref([
  {
    title: "mana application",
    description: "Financial application",
    icon: "i-heroicons-wallet",
    to: "https://mana2018.co.th"
  },
  {
    title: "License",
    description: "Financial license",
    icon: "i-material-symbols-light-currency-exchange",
    to: "certificate"
  }
]);
</script>