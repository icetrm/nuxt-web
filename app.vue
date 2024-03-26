<script setup lang="ts">
// definePageMeta({
//     title: 'My home page'
// });

useSeoMeta({
  title: 'Theramed Boonrod',
  ogTitle: 'Theramed Boonrod',
  description: 'This is my site.',
  ogDescription: 'This is my site.',
  // ogImage: 'https://example.com/image.png',
  // twitterCard: 'summary_large_image',
})

</script>
<template>
  <NuxtLayout>
    <v-app>
      <NuxtPage />
    </v-app>
  </NuxtLayout>
</template>