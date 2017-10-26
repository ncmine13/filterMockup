<template>
  <div>
    <h1> {{ name }} </h1>
    <h4> {{ title }} </h4>
    <p> {{ excerpt }} </p>
  </div>
</template>

<script>
  export default {
    name: 'Presenter',
    data () {
      return {
        name: this.presenter.name,
        title: this.presenter.title,
        excerpt: this.presenter.excerpt
      }
    },
    props: ['presenter']
  }
</script>

