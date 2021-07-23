<template>
  <h1> {{ title }} </h1>
  <p>Welcome...</p>
  <div v-if= "showModal">
  <Modal theme="" @close="toggleModal">
    <template v-slot:links>
      <a href="#">sign up now</a>
      <a href="#">more info</a>
    </template>
     <h1>Ninja Giveaway!</h1>
     <p>Grab your ninja swag for half price!</p>
  </Modal>
  </div>
  <button @click.alt="toggleModal">open modal (alt)</button>
  <!--<input type="text" ref="name">
 <button @click="handleClick">click me</button>-->
</template>

<script>
import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components: { Modal },
  data() {
    return{
      title: 'My First Vue App :)',
      header: 'SignUp for the Giveaway!',
      text: 'Grab your ninja swag for half price!',
      showModal: false
    }
  },
  
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
      
    }
  },

  /*methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()

    }
  },*/
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

h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
