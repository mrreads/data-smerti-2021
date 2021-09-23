<template>
    <div id="final">
        <div class="container">

            <p class="text-mini message"> Спасибо за Ваши ответы! <br> <strong> Мы подготовили для Вас <br> персональную аудио запись с <br> Вашим прогнозом. </strong> </p>
            
            <p class="text-mini">Вы можете узнать, как повлиять <br> на события, которые ожидают <br> вас в ближайшем будущем. </p>

            <div class="questions-wrapper">
                <p class="text-orange"> <strong> ПЕРВОЕ ЗНАЧИМОЕ <br> СОБЫТИЕ МОЖЕТ <br> ПРОИЗОЙТИ УЖЕ {{date}}, </strong> <br> <span> Вам надо быть готовым, что <br> бы последствия не оказались необратимыми. </span> </p>
                
                <p class="text-mini">Нажмите на кнопку ниже прямо <br> сейчас и наберите наш номер <br> телефона. Прослушайте важную информацию!</p>

                <button class="button blick" @click="call"> Позвонить и прослушать </button>
            </div>

            <p class="text-mini terms">TERMENI SI CONDITII: ACESTA ESTE UN SERVICIU DE <br> DIVERTISMENT. PRIN FOLOSIREA LUI DECLARATI CA AVETI 18 ANI IMPLINITI</p>
        </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            date: null
        }
    },
    methods: {
        call() 
        {
                fetch("https://swapi.dev/api/people/1/")
                .then(response => response.json())
                .then(result => 
                {
                    console.log(result)
                })
                .catch(error => console.log('error', error));
        }
    },
    mounted() {
        document.title = 'Результат';
        const date = new Date(new Date()).getDate() + 1;
        const month = new Date(new Date()).getMonth() + 1;
        const year = new Date(new Date()).getFullYear();
        this.date = `${date}.${month}.${year}`;
    }
}
</script>
