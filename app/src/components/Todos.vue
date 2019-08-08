<template>
    <div>
        <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" v-for="todo in todos" v-bind:key="todo.id"/>
    </div>
</template>


<script>
import TodoItem from "./TodoItem";

export default {
    name: "Todos",
    props: ["todos"],
    components: {
        TodoItem
    }
}
</script>

<style scoped>
    div {
        display: flex;
        flex-flow: column nowrap;
        justify-content: center;
        background: #fe4564;
    }
</style>