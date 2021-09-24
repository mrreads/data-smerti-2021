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

        <div class="popup" v-if="showPupup" data-aos="fade-left">
            <p class="text-orange">Данные из API</p>
            <p v-for="(value, name) in fetchData" :key="name"> <strong> {{name}}: </strong> <span>{{value}} </span> </p>
        </div>
  </div>
</template>

<style scoped>
.popup
{
    opacity: 0.9;
    display: flex;
    flex-flow: column nowrap;
    padding: 50px 25px;
    align-items: center;
    position: fixed;

    flex-grow: 1;

    width: 100vw;
    height: 100vh;

    background-color: #202024;
    z-index: 100;
    overflow-y: scroll;
    overflow-x: hidden;
}

.popup p
{
    margin: 5px 0;
}

.popup p strong
{
    text-transform: capitalize;
    margin-right: 5px;
    color: rgba(255, 255, 255, 0.6);

}

#final .popup .text-orange
{
    margin: 0 auto;
    margin-bottom: 25px;
    padding: 0;
    border: 0px;
}

@media screen and (max-width: 425px)
{
    .popup
    {
        font-size: 16px;
        line-height: 25px;
    }
}
</style>

<script>
export default {
    data() {
        return {
            date: null,

            showPupup: false,
            fetchData: null
        }
    },
    methods: {
        call() 
        {
                fetch("https://swapi.dev/api/people/1/")
                .then(response => response.json())
                .then(result => 
                {
                    this.fetchData = result;
                    this.showPupup = true;
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
