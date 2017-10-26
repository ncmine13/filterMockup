<template>
  <div>
    <div class="button-wrapper" v-if="seen">
      <div class="num" v-on:click="selectPresenter(presenter.id)" v-for="presenter in presenters" :key="presenter.id">{{ presenter.id }}</div>
    </div>
    <presenter :presenter="presenter" v-else></presenter>  
  </div>
</template>

<script>
  import presenter from './Presenter'
  export default {
    name: 'Filter',
    data () {
      return {
        msg: 'Click me to see presenter',
        seen: true,
        presenter: {
          name: '',
          title: '',
          excerpt: '',
          id: 0
        }
      }
    },
    props: ['presenters'],
    methods: {
      selectPresenter: function (selectedId) {
        let pres = this.presenters.filter(presenter => presenter.id === selectedId)
        this.presenter.name = pres[0].name
        this.presenter.title = pres[0].title
        this.presenter.excerpt = pres[0].excerpt
        this.presenter.id = pres[0].id
        console.log(this.presenter.id)
        this.seen = !this.seen
      }
    },
    components: {
      presenter
    }
  }
</script>

<style scoped>
  .button-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 50px;
    margin-top: 5%;
  }
  .num {
    padding: 10px 20px;
    margin: 20px;
    background-color: #6f7e96;
    font-size: 14px;
    border-radius: 3px;
  }
  .num:hover {
    transition: all 0.2s ease-in-out;    
    transform: scale(1.045);
  }
</style>
