<template>
    <span class="integer-view">{{ normalize() }}</span>
</template>

<script>
  export default {
    name: "integerView",
    props: {
      value: {
        type: [Number, String]
      }
    },
    methods: {
      normalize: function() { // demo only, we do not need such normalization here
        return parseInt(this.value, 10);
      }
    }
  }
</script>

<style scoped>

</style>