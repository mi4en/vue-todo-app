<template>
    <div>
        <h1>{{ msg }}</h1>
        <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem v-bind:todo="todo"/>
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
    name: 'Todos',
    components: {
        TodoItem
    },
    props: {
        msg: String,
        todos: Array
    }
}
</script>

<style scoped>

</style>


