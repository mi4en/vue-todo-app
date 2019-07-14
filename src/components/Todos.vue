<template>
    <div>
        <div v-bind:key="todoFromVForDirective.id" v-for="todoFromVForDirective in todosFromAppVue">
            <TodoItem 
                v-bind:todoFromVForDirective="todoFromVForDirective" 
                v-on:del-todo="$emit('del-todo', todoFromVForDirective.id)"  
                v-on:edit-todo="$emit('edit-todo', todoFromVForDirective.id)"/>
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
    props: ['todosFromAppVue']
}
</script>

<style scoped>

</style>


