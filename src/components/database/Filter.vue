<template>
  <div>
    <div class="filter-header" :key="filter.id" v-for="filter in filters">
      {{ filter.header }}
      <div></div>
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
          cats: [],
          id: 0
        }
      }
    },
    props: ['filters']
  }
</script>

<style>
  .filter-header {
    font-size: 16px;
  }
</style>
