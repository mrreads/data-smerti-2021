<template>
    <div id="test">
        <div class="container">

            <p class="text-magic"> Смерть родного человека – одно из <br> тяжелейших испытаний в жизни каждого из нас! </p>
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
