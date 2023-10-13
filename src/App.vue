<template>
  
    <h1>{{ title }}</h1>
    <p>Welcome..</p>
    
    <div v-if="showModal">
      <ModalTest  :header="header" :text="text" theme="sale"  @close="toggleModal"/>
    </div>
    <button @click="toggleModal">open modal</button>
  
</template>

<script>
 
 import ModalTest from './components/ModalTest.vue'

export default {
  name: 'App',
 components: {ModalTest}, 
  data() {
    return {
      title: 'hello world',
      text: ' Dont miss your chance to get a gift on your first membership.',
      header:'Sign up for the Giveaway!',
      showModal: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    }
  },
 
}
</script> 

<style scoped>
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
