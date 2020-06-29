<template>
  <div id="app">
    <Grid
      title="Some Table Title"
      :collection="collection"
      :columnsConfig="columnsConfig"
    />
  </div>
</template>

<script>
import Grid from "@/components/Grid";

const collection = [{
  id: 1,
  name: 'John',
  age: 22,
  gender: 'male',
  birthday: new Date('2001-05-04'),
  approved: true,
  description: 'Some description for John'
}, {
  id: 2,
  name: 'Jessica',
  age: 26,
  gender: 'female',
  birthday: new Date('1997-10-21'),
  approved: true,
  description: 'Some description for Jessica'
}, {
  id: 3,
  name: 'Silvester',
  age: 31,
  gender: 'male',
  birthday: new Date('1992-07-17'),
  approved: true,
  description: 'Some description for Silvester'
}];

export default {
  name: 'App',
  components: {
    Grid
  },
  data() {
    return {
      collection,
      columnsConfig: [{
        label: 'Name',
        dataKey: 'name',
        renderAs: 'String'
      }, {
        label: 'Age',
        dataKey: 'age',
        renderAs: 'Integer',
        sortable: true
      }, {
        label: 'Birthday',
        dataKey: 'birthday',
        renderAs: this.renderBirthday
      }, {
        label: 'Gender',
        dataKey: 'gender',
        renderAs: 'String'
      }, {
        label: 'Status',
        dataKey: 'approved',
        renderAs: 'Boolean'
      }, {
        label: 'Description',
        dataKey: 'description',
        renderAs: 'String'
      }]
    };
  },
  methods: {
    renderBirthday: function(value) {
      return value.toISOString();
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
