<template>
  <div id="add-container">
    <form @submit="addTodo" >
        <input type="text" v-model="title">
    </form>
  </div>
</template>

<script>
export default {
    name:'TodosAdd',
    data(){
        return{
            title:''
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault()

            const newTodo ={
                id:Math.random() * (10000 - 10) + 10,
                title:this.title,
                complete:false
            }
            this.title=''
            this.$emit('add-todo', newTodo)

        }
    }
}
</script>

<style>
    #add-container,input[type="text"]{
        padding: 10px;
    }
    input[type="text"]{
        outline: none;
        border: solid 1 px #ccc;
        width: 100%;
    }
</style>