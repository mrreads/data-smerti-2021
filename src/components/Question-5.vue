<template>
    <div id="test">
        <div class="container">

            <p class="text-magic message"> {{ message }} </p>
            <hr>

            <div class="questions-wrapper">
                <p class="text-orange">Запись, которую Вы услышите, <br> может шокировать людей с <br> неокрепшей психикой. Вы готовы <br> узнать, что ждет именно Вас?</p>
                
                <button class="button blick" @click="this.$parent.currentQuestion++">Да</button>
                <button class="button blick" @click="this.$parent.currentQuestion++"> Затрудняюсь ответить </button>
            </div>

            <p class="text-mini test-count">Вопрос 5-5</p>
        </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            message: null
        }
    },
    mounted() {
        document.title = 'Вопрос 5';
        const age = this.$parent.userAge;

        if (age >= 18 || age < 35)
        {
            this.message = "По вам скучает очень близкий человек, \n которого больше нет в мире живых.";
        }
        else  if (age >= 36 || age < 45)
        {
            this.message = 'По вам скучает очень близкий человек, \n которого больше нет в мире живых. \n Возможно это дедушка или бабушка.';
        }
        else
        {
            this.message = 'По вам скучает очень близкий человек, \n которого больше нет в мире живых. \n Возможно это кто-то из Ваших родителей.';
        }
    }
}
</script>
