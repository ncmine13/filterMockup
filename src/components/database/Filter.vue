<template>
  <div>
    <div class="filter-header" :key="filter.id" v-for="filter in filters">
      {{ filter.header }}
      <div class="filter-subcat" :key="value" v-for="value in filter.values"> {{ value }} </div>
    </div>
  </div>  
</template>

<script>
  export default {
    name: 'Filter',
    data () {
      return {
        msg: 'this is new filter meszage',
        filter: {
          header: '',
          values: [],
          id: 0
        }
      }
    },
    props: ['filters']
  }
</script>

<style>
  .filter-header {
    font-size: 18px;
    margin-bottom: 10px;
  }
  .filter-subcat {
    font-size: 14px;
    padding-left: 10px;
    margin-bottom: 5px;
  }
</style>
