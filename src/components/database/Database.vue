<template>
  <div id="db-wrapper">
    <p> {{ msg }} </p>
    <filterComponent :presenters="presenterData"></filterComponent>
  </div>
</template>


<script>
  import filterComponent from './Filter'
  // import data from '../../data/mock.json'
  import presenterData from '../../data/mock-presenter.json'
  export default {
    name: 'DatabasePage',
    data () {
      return {
        msg: 'this the database page',
        presenterData: presenterData
      }
    },
    components: {
      filterComponent
    }
  }
</script>

<style scoped>
  p {
    color: #e14d36;
    font-size: 16px;
  }
</style>