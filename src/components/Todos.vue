<template>
    <div>
        <ul  :key="todo.key" v-for="todo in todosList">
               <TodoItem :todo="todo" @delate-todo="$emit('delate-todo',todo.id)" />
        </ul>
    </div>
</template>

<script>
import TodoItem from './TodoItem'
export default {
    name:'Todos',
    props:['todosList'],
    components:{
        TodoItem
    }
}

</script>