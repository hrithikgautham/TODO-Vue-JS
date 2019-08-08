<template>
    <ul v-bind:class="{'is-complete': todo.completed}">
        <li>
            <input v-if="todo.completed" type="checkbox" v-on:change="markComplete" checked/>
            <input v-else type="checkbox" v-on:change="markComplete"/>
                {{ todo.title }}
            <button @click="$emit('del-todo', todo.id)" class="btn">X</button>
        </li>
    </ul>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete(e) {
            // console.log(1,2,3);
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
    ul {
        width: 100%;
        padding: 10px;
        margin-left: 20px;
    }
    ul:hover {
        cursor: pointer;
    }
    li {
        list-style-type: none;
        padding: 5px;
        background: lightblue;
    }
    .is-complete {
        background: lime;
        text-decoration: line-through;
    }
</style>
