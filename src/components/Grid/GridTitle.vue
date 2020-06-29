<template>
    <h4 class="grid-title">
        <slot></slot>
    </h4>
</template>

<script>
  export default {
    name: "GridTitle"
  }
</script>

<style scoped>
    .grid-title {
        border-bottom: 1px dotted inherit;
    }
</style>