<template>
    <div class="content">
        <SingleCard v-for="(item, index) in albums" :key="index" :poster="item.poster" :title="item.title" :author="item.author" :genre="item.genre" :year="item.year" />
    </div>
</template>

<script>
import SingleCard from "../secondary/SingleCard.vue";
export default {
    name: "MainContent",
    props: {
        albums: Array,
    },
    components: {
        SingleCard,
    },
};
</script>

<style scoped lang="scss">
.content {
    padding-top: 7rem;
    min-height: 100vh;
    width: 70%;
    margin: 0 auto;

    @media only screen and (max-width: 1000px) {
        width: 100%;
    }

    display: flex;
    flex-wrap: wrap;
}
</style>
