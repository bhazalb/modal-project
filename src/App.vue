<template>
  
    <h1>{{ title }}</h1>
    <p>Welcome..</p>
    
    <div v-if="showModal">
      <ModalTest  :header="header" :text="text" theme="sale"  @close="toggleModal">
<template v-slot:links>
  <a href="#">sign up now</a>
  <a href="#"> more info</a>
</template>
       <h1>Sign up for the Giveaway!</h1>
       <p>Dont miss your chance to get a gift on your first membership.</p>
</ModalTest>
    </div>
    <button @click="toggleModal">open modal</button>
    <button @click="toggleModalTwo">Detail</button>
   
    <div v-if="showModalTwo" >
      <ModalTest  @close="toggleModalTwo">
        <template v-slot:linksTwo>
        <a href="#">Okey</a>
        <a href="#">No , thanks</a>
        </template>

        <p>Dont miss your chance to get a gift on your first membership.</p>
      </ModalTest>
      
    </div>
  


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
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    }, 
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
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
button{
  width: 90px;
  height: 45px;
  background-color: black;
  border-radius: 4px;
  border: none;
  color: #ddd;
  margin: 5px;
  cursor: pointer;

}
</style>
