<template>
  <div>
    <div class="button-wrapper" v-if="seen">
      <div class="num" v-on:click="togglePresenter(presenter.id_json)" v-for="presenter in presenters" :key="presenter.id_json">
      <img class="bean" src="../../assets/bean.jpg" />
      <p class="name">{{ presenter.first_name + ' ' + presenter.last_name }}</p>
      <p> {{ presenter.title }} </p>
      </div>
    </div>
    <presenter :presenter="presenter" v-else></presenter>  
  </div>
</template>

<script>
  import presenter from './Presenter'
  export default {
    name: 'List',
    data () {
      return {
        msg: 'Click me to see presenter',
        seen: true,
        presenter: {
          first_name: '',
          last_name: '',
          title: '',
          excerpt: '',
          id_json: 0
        }
      }
    },
    props: ['presenters'],
    methods: {
      togglePresenter: function (selectedId) {
        if (this.seen) {
          let pres = this.presenters.filter(presenter => presenter.id_json === selectedId)[0]
          this.presenter = pres
          this.seen = !this.seen
        } else {
          this.seen = true
        }
      }
    },
    components: {
      presenter
    }
  }
</script>

<style scoped>
  .bean {
    max-width: 120px;
  }
  .button-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-left: 20%;
  }
  .num {
    padding: 10px 20px;
    margin: 0 20px;
    font-size: 14px;
    border-radius: 3px;
    cursor: pointer;
  }
</style>
