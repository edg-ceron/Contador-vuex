<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div>
      <h2>Contador</h2>
      <p>{{count}}</p>
      <p>{{getDouble}}</p>
    </div>
    <div>
      <button @click="increment">+</button>
      <button @click="decrement">-</button>
    </div>
    <div>
      <button @click="increment10">+10</button>
    </div>
  </div>
</template>

<script>

import { mapState, mapMutations, mapGetters } from 'vuex'

export default {
  name: 'app',

  computed: {
    ...mapState(['count']),

    ...mapGetters(['getDouble'])

  },

  methods: {
    ...mapMutations(['increment', 'decrement']),

    increment10(number) {
      this.$store.commit('increment', {
        number: 10
      })
    }
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
