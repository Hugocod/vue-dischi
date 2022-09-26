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
    width: 100%;
    background-color: #1e2d3b;

    display: flex;
    flex-wrap: wrap;
}
</style>
