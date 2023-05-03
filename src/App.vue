<script setup lang="ts">
import { ref } from 'vue'
import { PageWrapper, SiteHeader, SiteFooter, Contentselector } from '@/components'
import pageNames from '@/assets/data/pageNames'

const selectedPage = ref(pageNames[0])
</script>

<template>
 <PageWrapper>
  <template #header>
    <SiteHeader />
    <Contentselector
      v-model:selected-page="selectedPage"
      :page-names="pageNames"
    />
  </template>
  <div>
    Content
  </div>
  <template #footer>
    <SiteFooter />
  </template>
 </PageWrapper>
</template>

<style scoped>
</style>
