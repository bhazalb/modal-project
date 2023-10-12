<template>
    <div class="backdrop">
        <div class="modal">
            <h1>{{  header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>


<script>
export default {
    props: ['header', 'text']
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
h1{
color: rgb(18, 20, 126);
border: none;
padding: 0;
}
</style>