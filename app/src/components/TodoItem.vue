<template>
    <ul v-bind:class="{'is-complete' : todo.isCompleted}">
        <li>{{ todo.title }}</li>
    </ul>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"]
}
</script>

<style scoped>
    ul {
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
