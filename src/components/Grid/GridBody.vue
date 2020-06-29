<template>
    <tbody>
        <tr v-for="data in collection" :key="data.id">
            <td v-for="columnConfig in columnsConfig" :key="columnConfig.id">
                <StringView v-if="columnConfig.renderAs === 'String'" :value="data[columnConfig.dataKey]"></StringView>
                <IntegerView v-else-if="columnConfig.renderAs === 'Integer'" :value="data[columnConfig.dataKey]"></IntegerView>
                <BooleanView v-else-if="columnConfig.renderAs === 'Boolean'" :value="data[columnConfig.dataKey]"></BooleanView>
                <template v-else-if="typeof columnConfig.renderAs === 'function'">
                    {{ columnConfig.renderAs(data[columnConfig.dataKey]) }}
                </template>
            </td>
        </tr>
    </tbody>
</template>

<script>
  import StringView from "@/components/StringView";
  import IntegerView from "@/components/IntegerView";
  import BooleanView from "@/components/BooleanView";

  export default {
    name: "GridBody",
    components: {
      StringView,
      IntegerView,
      BooleanView
    },
    props: {
      columnsConfig: {
        type: Array,
        default: () => []
      },
      collection: {
        type: Array,
        default: () => []
      }
    },
    methods: {}
  }
</script>

<style scoped>

</style>