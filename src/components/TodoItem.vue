<template>
    <div class="todo-item" v-bind:class="{'is-complete':todoFromVForDirective.completed}">
        <p>
            <input type="checkbox" name="" id="" v-on:change="markComplete">
            {{ todoFromVForDirective.title }}
            <button class="del" @click="$emit('del-todo', todoFromVForDirective.id)">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ['todoFromVForDirective'],
    methods: {
        markComplete() {
            this.todoFromVForDirective.completed = !this.todoFromVForDirective.completed;
        }
    }
}
</script>

<style scoped>
.todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}

.is-complete {
    text-decoration: line-through;
}

.del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
}
</style>

