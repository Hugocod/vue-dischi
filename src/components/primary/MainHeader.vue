<template>
    <header>
        <img src="../../assets/logo.webp" alt="logo" />
        <select id="genre" v-model="userGenre" @change="$emit('genreIsChanged', userGenre)">
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="Rock">Rock</option>
        </select>
    </header>
</template>

<script>
export default {
    name: "MainHeader",
    data() {
        return {
            userGenre: "",
        };
    },
};
</script>

<style scoped lang="scss">
header {
    width: 100%;
    background-color: #2d3a46;

    position: fixed;
    top: 0;

    display: flex;
    justify-content: space-between;
    align-items: center;
    img {
        width: 2rem;
        padding: 1rem;
    }
}
</style>
