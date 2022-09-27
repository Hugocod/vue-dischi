<template>
    <div id="app">
        <MainHeader @genreIsChanged="getUserGenre($event)" />
        <MainContent :albums="filterByGenre" />
        <MainLoader v-if="loading" />
    </div>
</template>

<script>
import axios from "axios";
import MainContent from "./components/primary/MainContent.vue";
import MainHeader from "./components/primary/MainHeader.vue";
import MainLoader from "./components/primary/MainLoader.vue";

export default {
    name: "App",
    data() {
        return {
            albumData: [],
            filteredAlbums: [],
            dataUrl: "https://flynn.boolean.careers/exercises/api/array/",
            loading: true,
            userGenre: "All",
        };
    },
    components: { MainContent, MainHeader, MainLoader },
    created() {
        /////////////////////////////////////////////////////////////////////////
        ///////////////////////////////////////////////////////////////////////// Recupera i dati dall'API
        axios
            .get(this.dataUrl + "music")
            .then(({ status, data }) => {
                this.loading = false;
                if (status === 200) {
                    this.albumData = data.response;
                }
            })
            .catch((error) => {
                console.log(error);
                this.loading = false;
            });
        /////////////////////////////////////////////////////////////////////////
        /////////////////////////////////////////////////////////////////////////
    },
    methods: {
        getUserGenre: function (userChoice) {
            /////////////////////////////////////////////////////////////////////////
            /////////////////////////////////////////////////////////////////////////
            this.userGenre = userChoice;
            this.filteredAlbums = [];
            /////////////////////////////////////////////////////////////////////////
            /////////////////////////////////////////////////////////////////////////
        },
    },

    computed: {
        filterByGenre: function () {
            /////////////////////////////////////////////////////////////////////////
            /////////////////////////////////////////////////////////////////////////

            this.albumData.forEach((album) => {
                if (this.userGenre === "All") {
                    this.filteredAlbums = this.albumData;
                } else if (album.genre === this.userGenre) {
                    this.filteredAlbums.push(album);
                } else {
                    return null;
                }
            });

            return this.filteredAlbums;
            /////////////////////////////////////////////////////////////////////////
            /////////////////////////////////////////////////////////////////////////
        },
    },
};
</script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;

    background-color: #1e2d3b;
}

body {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "M PLUS Rounded 1c", sans-serif;
}

h1,
h2,
h3,
h4,
p {
    margin: 0;
    padding: 0;
    font-family: "M PLUS Rounded 1c", sans-serif;
}
</style>
