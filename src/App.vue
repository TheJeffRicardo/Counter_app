<template>
  <div class="container bg-secondary">
    <div class="row">
      <div class="col">
        <div class="form">
          <div>
            <input type="text" placeholder="0" :value="counter" readonly>
          </div>
        </div>
        <div class="row">
          <div class="col">
            <button class="btn btn-danger" @click.prevent="decrease">Decrease</button>
          </div>
          <div class="col">
            <button class="btn btn-success" @click.prevent="increase">Increase</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  //How we access our state it must be returned
  computed: {
    counter(){
      return this.$store.state.counter
    }
  },
  //Any component that has been displayed on the browser
  // unmounted - when a component is remove
  methods: {
    increase() {
      this.$store.dispatch('increaseCounter')
    },
    decrease() {
      this.$store.dispatch('decreaseCounter')
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
