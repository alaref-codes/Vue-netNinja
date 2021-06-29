<template>
  <div v-if="showModal" >
      <Modal header="Modal 1 homie" theme="d" @close="toggleM"  />
  </div>
  <button @click="toggleM" >show modal 1 </button>

  <div v-if="showModalTwo" >
      <Modal header="Modal 2 homie" theme="d" @close="toggleM2"  />
  </div>
  <button @click="toggleM2" >show modal 2 </button>
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
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleM() {
      this.showModal = !this.showModal
    },
    toggleM2() {
      this.showModalTwo = !this.showModalTwo
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
