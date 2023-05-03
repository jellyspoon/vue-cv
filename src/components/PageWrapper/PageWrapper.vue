<script setup lang="ts">
</script>

<template>
  <div class="page-wrapper">
    <div class="page-wrapper--header">
      <slot name="header"></slot>
    </div>
    <div class="page-wrapper--content">
      <slot></slot>
    </div>
    <div class="page-wrapper--footer">
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<style scoped lang="scss">
.page-wrapper {
  margin-left: auto;
  margin-right: auto;
  max-width: 100ch;
  height: 100%;
  max-height: 100%;
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
}
.page-wrapper--header {
  background-color: $highlight;
}
.page-wrapper--content {
  background-color: $highlight;
  flex-grow: 1;
  overflow-y: auto;
}
.page-wrapper--footer {
  background-color: $highlight;

}
</style>
