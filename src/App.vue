<template>
    <div id="app">
        <MainHeader @genreIsChanged="takeGenre($event)" />
        <MainContent :albums="albumData" />
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
            dataUrl: "https://flynn.boolean.careers/exercises/api/array/",
            loading: true,
            indexGenre: "ciao",
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
                    console.log(data);
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
        takeGenre: function (e) {
            console.log(e);
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
