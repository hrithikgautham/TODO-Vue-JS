<template>
    <header>
        <h1>Todo List</h1>
        <ul>
            <li>Home</li>
            <li>Games</li>
            <li>Contact</li>
            <li>Subscribe</li>
        </ul>
    </header>    
</template>

<script>
export default {
    name: "Header"
}
</script>

<style scoped>
    header {
        display: flex;
        padding: 10px;
        justify-content: space-between;
        align-items: center;
        background: blue;
    }
    header ul {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 60vw;
    }
    header ul li {
        list-style-type: none;
        padding: 10px;
    }
    header ul li:hover {
        background: lightblue;
        cursor: pointer;
    }
</style>

