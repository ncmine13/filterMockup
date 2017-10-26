<template>
  <div>
    <h1> {{ name }} </h1>
    <p> {{ title }} </p>
    <p> {{ excerpt }} </p>
    <div class="back" v-on:click="back()"> {{ btnMsg }} </div>
  </div>
</template>

<script>
  export default {
    name: 'Presenter',
    data () {
      return {
        btnMsg: 'back to presenter list',
        name: this.presenter.first_name,
        title: this.presenter.title,
        excerpt: this.presenter.excerpt
      }
    },
    props: ['presenter', 'seen'],
    methods: {
      back: function () {
        this.$parent.togglePresenter()
      }
    }
  }
</script>

<style scoped>
  p {
    font-size: 16px;
    font-weight: lighter;
  }
  h1 {
    margin: 100px 0 20px 0;
  }
  .back {
    margin-top: 40px;
    font-size: 14px;
    background-color: #c45c4c;
    width: 15%;
    text-align: center;
    padding: 10px 5px;
    border-radius: 2px;
    color: black
  }
  .back:hover {
    margin-top: 43px;
    transition: all 0.2s ease-in-out;    
    transform: scale(1.045);
  }
</style>

