<template>
    <span class="string-view">{{ value }}</span>
</template>

<script>
  export default {
    name: "StringView",
    props: {
      value: String
    }
  }
</script>

<style scoped>

</style>