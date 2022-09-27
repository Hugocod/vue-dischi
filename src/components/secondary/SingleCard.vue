<template>
    <div class="card">
        <figure>
            <!-- il ternario serve a correggere l'errore nella API -->
            <img :src="poster === 'https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg' ? 'http://www.scottishculture.org/themes/scottishculture/images/music_placeholder.png' : poster" :alt="title" />
            <h1>{{ title }}</h1>
            <h2>{{ author }}</h2>
            <h2>{{ year }}</h2>
        </figure>
    </div>
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
.card {
    width: calc(100% / 5);

    @media only screen and (max-width: 1100px) {
        width: calc(100% / 4);
    }
    @media only screen and (max-width: 700px) {
        width: calc(100% / 3);
    }
    @media only screen and (max-width: 500px) {
        width: calc(100% / 2);
    }
    @media only screen and (max-width: 400px) {
        width: 100%;
    }
}

figure {
    /*  display: flex;
    flex-direction: column; */

    background-color: #2d3a46;

    margin: 1rem;
    padding: 1rem;
    border-radius: 1.1rem;

    img {
        width: 100%;
    }

    h1 {
        color: white;
        font-size: 1rem;
        text-transform: uppercase;
        padding: 1rem 0;
    }

    h2 {
        color: rgb(184, 172, 172);
        font-size: 0.8rem;
    }
}
</style>
