<template>
    <figure>
        <img :src="poster" :alt="title" />
        <h1>{{ title }}</h1>
        <h2>{{ author }}</h2>
        <h2>{{ genre }}</h2>
        <h2>{{ year }}</h2>
    </figure>
</template>

<script>
export default {
    name: "SingleCard",
    props: {
        poster: String,
        title: String,
        author: String,
        genre: String,
        year: String,
    },
};
</script>

<style scoped lang="scss">
.content {
    width: 100%;
    background-color: rgb(96, 186, 186);
}

.card {
    background-color: red;
    margin: 2rem;
}

figure {
    display: flex;
    flex-direction: column;

    width: calc(100% / 6);

    background-color: #2d3a46;

    h1 {
        color: white;
        font-size: 1rem;
        text-transform: uppercase;
    }
}
</style>
