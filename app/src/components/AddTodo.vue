<template>
    <form @submit="addTodo">
        <label>
            <input v-model="title" placeholder="Todo Title" type="text"/>
        </label>
        <label>
            <input type="submit" value="submit"/>
        </label>
    </form>
</template>

<script>
export default {
    name: "AddTodo",
    data() {
        return {
            title: ""
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const todo = {
                title: this.title,
                completed: false
            };
            this.$emit('add-todo', todo);
            this.title = "";
        }
    }
}
</script>

<style scoped>
    form {
        width: 100%;
        background: lightcoral;
        display: flex;
        justify-content: center;
    }
    input[type="text"] {
        /* flex-basis: auto; */
        flex-basis: fit-content;
    }
    input[type="submit"] {
        /* width: 18%; */
        flex-basis: fit-content;
    }
</style>
