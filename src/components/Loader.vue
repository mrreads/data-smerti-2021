<template>
    <div id="loader">
        <img src="./../assets/img/loading.png" alt="Загрузка">
        <p>Loading</p>
    </div>
</template>

<style scoped>
    #loader
    {
        display: flex;
        flex-flow: column nowrap;
        justify-content: center;
        align-items: center;
        position: fixed;

        flex-grow: 1;

        width: 100vw;
        height: 100vh;

        background-color: #202024;
        z-index: 100;
    }

    #loader p
    {
        margin-top: 25px;
        color: rgba(255, 255, 255, 0.6);
    }

    @keyframes rotate 
    {
        from
        {
            transform: rotate(0deg);
        }
        to
        {
            transform: rotate(360deg);
        } 
    }
    #loader img
    {
        animation: rotate 3s infinite;
    }
</style>

<script>
export default {
  mounted() {
    document.title = 'Подождите';
  }
}
</script>