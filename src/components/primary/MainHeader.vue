<template>
    <header>
        <div class="wrapper">
            <img src="../../assets/logo.webp" alt="logo" />
            <select id="genre" v-model="userGenre" @change="$emit('genreIsChanged', userGenre)" value="All">
                <option value="All">All</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
                <option value="Rock">Rock</option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: "MainHeader",
    data() {
        return {
            userGenre: "All",
        };
    },
};
</script>

<style scoped lang="scss">
.wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;

    width: 95%;
    margin: 0 auto;
    padding: 1rem 0rem;
}
header {
    width: 100%;
    background-color: #2d3a46;

    position: fixed;
    top: 0;

    img {
        width: 2rem;
    }

    select {
        border: 0px;
        outline: 0px;
        border-radius: 5px;
        padding: 0.4rem 1rem;
        background-color: rgb(27, 215, 96);
        color: white;
        font-size: 1.2rem;
        font-weight: 600;
    }
}
</style>
