<script setup lang="ts">
import { PageWrapper, SiteHeader, SiteFooter } from '@/components'
</script>

<template>
 <PageWrapper>
  <template #header>
    <SiteHeader />
  </template>
  Content
  <template #footer>
    <SiteFooter />
  </template>
 </PageWrapper>
</template>

<style scoped>
</style>
