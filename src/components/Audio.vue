<template>
    <div id="audio">
        <img src="./../assets/img/audio.png" alt="Микрофон">

        <div class="progress-bar">
            <div class="progress" ref="progress"></div>
        </div>

        <p class="percent">{{percent}}%</p>
        <p class="text-mini">Запись сообщения</p>
    </div>
</template>

<style scoped>
    #audio
    {
        position: fixed;
        z-index: 100;

        display: flex;
        align-items: center;
        flex-flow: column nowrap;
        flex-grow: 1;
        justify-content: center;

        width: 100vw;
        height: 100vh;

        background-color: #202024;
    }

    #audio p
    {
        margin-top: 25px;

        color: rgba(255, 255, 255, 0.6);
    }

    .progress-bar
    {
        position: relative;

        width: 80%;
        height: 4px;
        margin: 30px 25px;

        border-radius: 5px;
        background: #FFFFFF;
    }

    .progress
    {
        position: absolute;
        top: 0;
        left: 0;

        width: 0%;
        height: 100%;
        height: 4px;

        border-radius: 5px;
        background: #F6C866;
    }

    #audio .percent
    {
        font-size: 20px;
        line-height: 23px;
        letter-spacing: 0.1em;

        color: rgba(255, 255, 255, 0.6);
    }

    #audio .text-mini
    {
        color: rgba(255, 255, 255, 0.6);

    }
</style>

<script>
export default {
    data() {
        return {
            percent: 0
        }
    },
    created() {
        setInterval(() => {
            if (this.percent < 100)
                this.percent++;

            this.$refs['progress'].style.width = `${this.percent}%`;
        }, 150)
    }
}
</script>