<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  pageNames: string[]
  selectedPage: string
}>()

// eslint-disable-next-line func-call-spacing
defineEmits<{
  (e: 'update:selectedPage', pageName: string): void
}>()

const columns = computed(() => props.pageNames.length)
const leftMargin = computed(() => props.pageNames.findIndex(p => p === props.selectedPage) + 'fr')
const rightMargin = computed(() => (props.pageNames.length - (props.pageNames.findIndex(p => p === props.selectedPage) + 1)) + 'fr')
</script>

<template>
  <div class="content-selector--wrapper">
    <div class="content-selector--grid">
      <div
        v-for="pageName in pageNames"
        :key="pageName"
        @click="$emit('update:selectedPage', pageName)"
      >
        {{ pageName }}
      </div>
    </div>
    <div class="content-selector--selected">
      <div />
      <div />
      <div />
    </div>
  </div>
</template>

<style scoped lang="scss">
.content-selector--grid {
  display: flex;
  justify-content: center;
  overflow: hidden;
}
.content-selector--grid {
  display: grid;
  grid-template-columns: repeat(v-bind(columns), 1fr);
  height: 3rem;
  div {
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    cursor: pointer;
    transition: background-color .2s;
  }
  div:hover {
    background-color: $highlight;
  }
}
.content-selector--selected {
  display: grid;
  grid-template-columns: v-bind(leftMargin) 1fr v-bind(rightMargin);
  transition: grid-template-columns 1s;
  div {
    height: 3px;
  }
  div:nth-child(2) {
    background-color: $primary;
  }
}
</style>
