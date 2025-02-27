<template>
  <div>
    <h1>{{ title }}</h1>
    <p>Welcome...</p>

    <Teleport to=".modals" v-if="showModal">
      <Modal theme="sale" @close="toggleModal">
        <template v-slot:links>
          <a href="#">Sign Up now</a>
          <a href="#">More Info</a>
        </template>
        <h1>Jaimy Mathon</h1>
        <p>Junior Developer</p>
      </Modal>
    </Teleport>

    <Teleport to=".modals" v-if="showModalTwo">
      <Modal theme="sale" @close="toggleModalTwo">
        <template v-slot:small-text >
            <p>This is a small text above everything</p>
        </template>
        <h1>Another modal form</h1>
        <p>This is the second one opened with shift</p>
      </Modal>
    </Teleport>

    <button @click.alt="toggleModal">Open Modal (alt)</button>
    <button @click.shift="toggleModalTwo">Open Modal (shift)</button>
  </div>  
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: "My First Vue App",
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
