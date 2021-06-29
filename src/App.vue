<template>
  <div v-if="showModal" >
      <Modal header="Display message" theme="d" @close="toggleM"  />
  </div>
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      showModal: true,
    }
  },
  methods: {
    toggleM() {
      this.showModal = !this.showModal
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
