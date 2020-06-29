<template>
    <div class="grid">
        <GridTitle v-if="title">{{ title }}</GridTitle>
        <table class="grid-table">
            <GridHeader :columnsConfig="columnsConfig" />
            <GridBody :columnsConfig="columnsConfig" :collection="collection" />
        </table>
    </div>
</template>

<script>
  import GridTitle from "@/components/Grid/GridTitle";
  import GridHeader from "@/components/Grid/GridHeader";
  import GridBody from "@/components/Grid/GridBody";

  export default {
    name: "GridGenerator",
    components: {
      GridTitle,
      GridHeader,
      GridBody
    },
    props: {
      title: String,
      columnsConfig: {
        type: Array,
        default: function() { return []; }
      },
      collection: {
        type: Array,
        default: function() { return []; }
      }
    }
  }
</script>

<style scoped type="scss">
    .grid-table {
        width: 100%;
    }
</style>