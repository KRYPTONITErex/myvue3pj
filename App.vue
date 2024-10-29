
<template>
  <h1 ref="greet">This is Vue CLI learning</h1><br>
  <h3>I am studying now</h3><br>
  <h2>{{ title }}</h2><br>

  <input type="text" ref="name">
  <button @click="clickhandler">click</button>

  <div v-if="showModal">
    <Modal :header="header" :content="content" :theme="theme" 
    @closeModal="showModal=false"/>
  </div>
  <button @click.shift="showModal=true">Open Modal</button>



</template>

<script>
import Modal from './components/components/Modal.vue';
export default {
  data(){
    return{
      header: true,
      content: "GOOD, you are fucking the same person",
      theme: "delete",
      showModal: false
    }
  },
  methods:{
    clickhandler(){
      this.$refs.name.focus();
      this.$refs.greet.textContent="Greeting"
    }
  },
  components:{
      Modal
    }
}
</script>

<style scoped >
h1{
  font-style: italic;
  font-display: auto;
  color: rgb(62, 114, 170);
  font-weight: 600;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
h2{
  font-weight: 600;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
h3{
  text-align: center;
  font-weight: bold;
  color: aliceblue;
  background-color: brown;
  align-items: center;
  text-align: center;
  margin-top: 10px;
  padding: 10px;
}
button{
  font-weight: 600;
  padding: auto;
  padding-left: 20px;
  padding-right: 20px;
  margin: 10px;
  box-shadow: 2px 2px 3px;
}


</style>