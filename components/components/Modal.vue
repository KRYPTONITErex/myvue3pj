<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{success:theme==='success', danger:theme==='delete'}" >
            <h2>{{header}}</h2>
            <p>{{content}}</p>

            <p>{{ theme }}</p>

        </div>
    </div>
  
</template>

<script>
export default {

    props: ['header','content','theme'],
    methods: {
        closeModal(){
            // alert("Hi")
            this.$emit("closeModal")
        }
    }

}
</script>

<style>
.backdrop{
    position: fixed;
    top: 0;
    background: rgba(2, 54, 50, 0.5);
    width: 100%;
    height: 100%;
}
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background-color: white;
    border-radius: 10px;
}

p{
    font-family: Arial, Helvetica, sans-serif;
    /* font-style: normal !important; */
    /* color: rgb(30, 0, 255)!important; */
}
.success{
    background-color: green;
    color: white  !important;;
}
.danger{
    background-color: crimson;
    color: wheat;
}
</style>