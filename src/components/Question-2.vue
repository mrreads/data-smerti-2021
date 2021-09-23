<template>
    <div id="test">
        <div class="container">

            <p class="text-magic"> Мы расскажем Вам не только подробности <br> вашей смерти, но также поможем Вам <br> избежать этой ужасной даты и продлить <br> вашу жизнь на многие годы. </p>
            <hr>

            <div class="questions-wrapper">
                <p class="text-orange">КОГДА ВЫ ЧУВСТВУЕТЕ СЕБЯ <br> НАИБОЛЕЕ КОМФОРТНО?</p>
                
                <button class="button blick" @click="this.$parent.currentQuestion++"> Утро</button>
                <button class="button blick" @click="this.$parent.currentQuestion++"> День </button>
                <button class="button blick" @click="this.$parent.currentQuestion++"> Вечер </button>
                <button class="button blick" @click="this.$parent.currentQuestion++"> Ночь </button>
            </div>


            <p class="text-mini test-count">Вопрос 2-5</p>
        </div>
  </div>
</template>

<script>
export default {
  mounted() {
    document.title = 'Вопрос 2';
  }
}
</script>