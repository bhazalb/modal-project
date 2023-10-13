<template>
    <div class="backdrop" @click="closeModal">
        <div class="modal" :class="{sale : theme === 'sale'}">
            <h1>{{  header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>


<script>
export default {
    props: ['header', 'text' , 'theme'],
    methods: {
        closeModal(){
            this.$emit('close')
        }
    },
}
</script>



<style>
.modal{
    width: 400px;
    padding: 20px;
   margin: 100px auto;
   background: white;
   border-radius: 10px;
}

.backdrop{
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.521);
    width: 100%;
    height: 100%;
    padding: 0;
    left: 0px;
}
.modal h1{
    color: rgb(75, 77, 78);
    border: none;
    padding: 0;
}
.modal p{
    font-style: italic;
}
.modal.sale{
    background: cornflowerblue;
    color: white;
}.modal.sale h1{
    color: rgb(4, 5, 85);
}
</style>