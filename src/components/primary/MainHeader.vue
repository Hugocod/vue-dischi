<template>
    <header>
        <img src="../../assets/logo.webp" alt="logo" />
    </header>
</template>

<script>
export default {
    name: "MainHeader",
};
</script>

<style scoped lang="scss">
header {
    width: 100%;
    background-color: #2d3a46;

    position: fixed;
    top: 0;

    display: flex;
    justify-content: start;
    align-items: center;
    img {
        width: 2rem;
        padding: 1rem;
    }
}
</style>
