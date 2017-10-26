<template>
  <div>
    <div class="button-wrapper" v-if="seen">
      <div class="num" v-on:click="togglePresenter(presenter.id_json)" v-for="presenter in presenters" :key="presenter.id_json">{{ presenter.first_name + ' ' + presenter.last_name }}</div>
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
    computed: {
      fullName: function () {
        return this.first_name + ' ' + this.last_name
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
