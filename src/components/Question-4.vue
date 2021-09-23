<template>
    <div id="test">
        <div class="container">

            <p class="text-magic"> Мы расскажем Вам не только подробности <br> вашей смерти, но также поможем Вам <br> избежать этой ужасной даты и продлить <br> вашу жизнь на многие годы. </p>
            <hr>

            <div class="questions-wrapper">
                <p class="text-orange">СНЯТЬСЯ ЛИ ВАМ УМЕРШИЕ ЛЮДИ?</p>
                
                <button class="button blick" @click="this.$parent.currentQuestion++"> Да</button>
                <button class="button blick" @click="this.$parent.currentQuestion++"> Нет </button>
                <button class="button blick" @click="this.$parent.currentQuestion++"> Иногда </button>
            </div>


            <p class="text-mini test-count">Вопрос 4-5</p>
        </div>
  </div>
</template>

<script>
export default {
    created() {
        this.$parent.loaderVisible = true;
        setTimeout(()=> {
            this.$parent.loaderVisible = false;
        }, 2000);
    }
}
</script>
