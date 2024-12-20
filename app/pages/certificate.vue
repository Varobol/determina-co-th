<template>
  <div>
    <UPage>
      <UPageBody :ui="{ wrapper: 'mt-0 pb-0' }">
        <ULandingSection title="License">
          <img src="https://failfast.blob.core.windows.net/upload/webdetermina/cerf/cerf1.jpg"
            class="mx-auto w-full h-full " />
            <img src="https://failfast.blob.core.windows.net/upload/webdetermina/cerf/cerf2.jpg"
            class="mx-auto w-full h-full " />
            <img src="https://failfast.blob.core.windows.net/upload/webdetermina/cerf/cerf3.jpg"
            class="mx-auto w-full h-full " />
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

</script>