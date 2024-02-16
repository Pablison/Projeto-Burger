<template>
    <footer id="footer">
        <p>Make Your Burger &copy; 2024</p>
    </footer>
</template>

<script>
    export default {
        name: "Footer"
    }
</script>

<style scoped>
    footer#footer {
        height: 100px;
        background-color: #222;
        border-top: 4px solid #111;
        color: #fcba03;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        bottom: 0;
        position: fixed;
    }
</style>