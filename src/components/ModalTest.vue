<template>
    <div class="backdrop" @click="closeModal">
        <div class="modal" :class="{sale : theme === 'sale'}">
          <!--  <h1>{{  header }}</h1>
            <p>{{ text }}</p>-->
            <slot></slot>
            <div class="actions">
                <slot name="links"> </slot>
            </div>
            
            <div class="actions">
           <slot name="linksTwo"></slot>
            </div>

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
.modal .actions{
    text-align: center;
    margin: 30px 0 10px 0;
    color: rgb(78, 45, 59);
}
.modal .actions a{
    color: rgb(78, 45, 59);
    padding: 8px;
    border: 1px solid #eeee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}
</style>