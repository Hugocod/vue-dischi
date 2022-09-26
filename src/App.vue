<template>
    <div id="app">
        <MainContent :albums="albumData" />
    </div>
</template>

<script>
import axios from "axios";
import MainContent from "./components/primary/MainContent.vue";

export default {
    name: "App",
    data() {
        return {
            albumData: "",
            dataUrl: "https://flynn.boolean.careers/exercises/api/array/",
            loading: true,
        };
    },
    components: { MainContent },
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
};
</script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

body {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
</style>
