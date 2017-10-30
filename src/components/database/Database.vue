<template>
  <div id="db-wrapper">
    <p> {{ msg }} </p>
    <div class="component-wrapper">
      <filter-component :filters="paramData" ></filter-component>
      <list-component :presenters="presenterData"></list-component>
    </div>
  </div>
</template>


<script>
  import listComponent from './List'
  import filterComponent from './Filter'
  import presenterData from '../../data/mock-presenter.json'
  import paramData from '../../data/filter-params.json'

  export default {
    name: 'DatabasePage',
    data () {
      return {
        msg: 'this the database page',
        presenterData: presenterData,
        paramData: paramData
      }
    },
    components: {
      listComponent,
      filterComponent
    }
  }
</script>

<style scoped>
  p {
    color: #e14d36;
    font-size: 16px;
  }
  .component-wrapper {
    display: flex;
    margin-top: 5%;
  }
</style>