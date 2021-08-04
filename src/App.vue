<template>
  <h1>{{ title }}</h1>
  <br>
  <input type="text" ref="name">
  <br>
  <button v-on:click="handleClick">Click Me</button>
  <br>
  <div v-if="showModal">
    <Modal :header="header" :text="text" :theme="theme" @closeModal="handleShowModal"/>
  </div>
  <button @click="handleShowModal">Show Modal</button>
</template>

<script>
import Modal from './components/modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data () {
    return {
      title: 'My first Vue.JS App :)',
      header: 'Sign-Up for a Vue Bootcamp',
      text: 'Another line of text.',
      theme: 'sale',
      showModal: false
    }
  },
  methods: {
    handleClick () {
      console.log(this.$refs.name)
      this.$refs.name.classList.toggle("active")
      this.$refs.name.focus()
    },
    handleShowModal () {
      this.showModal = !this.showModal
    }
  }
}
</script>