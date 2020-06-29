<template>
    <thead>
        <tr>
            <th class="grid-header-cell" v-for="columnConfig in columnsConfig" :key="columnConfig.id">
                {{ columnConfig.label }}
                <span v-if="columnConfig.sortable">&darr;</span>
            </th>
        </tr>
    </thead>
</template>

<script>

  export default {
    name: "GridHeader",
    props: {
      columnsConfig: {
        type: Array,
        default: function() { return []; }
      }
    }
  }
</script>

<style scoped>
    .grid-header-cell {
        text-align: left;
    }
</style>