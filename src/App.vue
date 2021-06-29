<template>
  <Modal />
  <input type="text" ref="nice">
  <button @click="handleClick">click</button>
  <h5 id="meg" ></h5>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  methods: {
    handleClick() {
      this.$refs.nice.focus();
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
