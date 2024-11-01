<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{success: theme === 'success', danger: theme === 'delete'}">
        
            <slot>
            default
            </slot>

            <slot name="links"></slot>

        </div>

    </div>

 
</template>

<script>
export default {

    props: ['theme'],
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
    background-color: rgba(212, 158, 21, 0.955);
    color: white  !important;;
}
.danger{
    background-color: crimson;
    color: wheat;
}
h3{
    color: rgb(124, 228, 178);
}

</style>