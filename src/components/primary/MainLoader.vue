<template>
    <div class="back">
        <div class="loader"></div>
    </div>
</template>

<script>
export default {
    name: "MainLoader",
};
</script>

<style scoped lang="scss">
.back {
    height: 100vh;
    width: 100%;
    background-color: #1cd760;
    position: fixed;
    top: 0;
    left: 0;

    display: flex;
    justify-content: center;
    align-items: center;

    .loader {
        border: 16px solid #f3f3f3; /* Light grey */
        border-top: 16px solid #2d3a46; /* Blue */
        border-radius: 50%;
        width: 120px;
        height: 120px;
        animation: spin 2s linear infinite;
    }

    @keyframes spin {
        0% {
            transform: rotate(0deg);
        }
        100% {
            transform: rotate(360deg);
        }
    }
}
</style>
