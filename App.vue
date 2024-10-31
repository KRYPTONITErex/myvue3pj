
<template>
  <h1 ref="greet">This is Vue CLI learning</h1><br>
  <h3 style="color: antiquewhite;">I am studying VUE CLI now</h3><br>
  <h2 style="color: darkred;">{{ title }}</h2><br>

  <h3>This is added for git push test</h3>

  <input id="ph" type="text" ref="name">
  <button @click="clickhandler">click</button>
  <BR></BR>

  <div class="Modals" v-if="showModal">
    <Modal :theme="theme" 
    @closeModal="showModal=false">

    <h2>LOGIN SUCCESS</h2>
    <p>WELCOME USER </p>

    <template v-slot:links>
      <a href="" style="color: antiquewhite;">Sign Up</a>&nbsp;&nbsp;
      <a href="" style="color: aliceblue;">Register</a>
    </template>

  </Modal>
  </div>
  <button @click="showModal=true">Open Modal</button>

  <div class="Modals" v-if="showMyModal">
    <Modal :theme="theme" 
    @closeModal="showMyModal=false">

    <h2>LOGIN MY MODAL SUCCESS</h2>
    <p>WELCOME USER BROS , HOW IS IT</p>

    <template v-slot:links>
      <a href="" style="color: antiquewhite;">Log IN</a>&nbsp;&nbsp;
      <a href="" style="color: wheat;">Log OUT</a>
    </template>

  </Modal>
  </div>
  <button @click="showMyModal=true">Open My Modal ... </button>


  

</template>

<script>
import Modal from './components/components/Modal.vue';
export default {
  data(){
    return{
      // header: true,
      // content: "GOOD, you are fucking the same person",
      theme: "delete",
      showModal: false,
      showMyModal: false,
      title: "Hi - I am Title sentence"
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
  color: rgb(21, 62, 112);
  font-weight: 600;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
h2{
  align-content: center;
  font-weight: 600;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  margin-left: 100px;
}
h3{
  text-align: center;
  font-weight: bold;
  color: rgb(219, 235, 248);
  background-color: brown;
  align-items: center;
  text-align: center;
  margin-top: 10px;
  margin-left: 20px;
  margin-right: 20px;
  padding: 20px;
  box-shadow: 10px 10px;
  border-radius: 5px;
}
button{
  font-weight: 600;
  padding: auto;
  padding-left: 20px;
  padding-right: 20px;
  margin: 10px;
  box-shadow: 2px 2px 3px;
}
#ph{
  margin-left: 80px;
}
button{
  padding-left: 20px;
  padding: 5px;
  background-color: rgb(38, 95, 100);
  color: rgb(231, 238, 239);
  margin-left: 50px;
  border-radius: 5px;
  box-shadow: 5px 5px;
  border: 1px solid grey;
}


</style>