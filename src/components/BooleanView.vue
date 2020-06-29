<template>
    <span class="boolean-view" v-if="value === true">v</span>
    <span class="boolean-view" v-if="value === false">X</span>
</template>

<script>
  export default {
    name: "BooleanView"
  }
</script>

<style scoped>

</style>