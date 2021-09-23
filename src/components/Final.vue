<template>
    <div id="final">
        <div class="container">

            <p class="text-mini message"> Спасибо за Ваши ответы! <br> <strong> Мы подготовили для Вас <br> персональную аудио запись с <br> Вашим прогнозом. </strong> </p>
            
            <p class="text-mini">Вы можете узнать, как повлиять <br> на события, которые ожидают <br> вас в ближайшем будущем. </p>

            <div class="questions-wrapper">
                <p class="text-orange">ПЕРВОЕ ЗНАЧИМОЕ <br> СОБЫТИЕ МОЖЕТ <br> ПРОИЗОЙТИ УЖЕ {{date}}, <br> <span> Вам надо быть готовым, что <br> бы последствия не оказались необратимыми. </span> </p>
                
                <p class="text-mini">Нажмите на кнопку ниже прямо <br> сейчас и наберите наш номер <br> телефона. Прослушайте важную информацию!</p>

                <button class="button blick"> Позвонить и прослушать </button>
            </div>

            <p class="text-mini terms">TERMENI SI CONDITII: ACESTA ESTE UN SERVICIU DE <br> DIVERTISMENT. PRIN FOLOSIREA LUI DECLARATI CA AVETI 18 ANI IMPLINITI</p>
        </div>
  </div>
</template>

<style scoped>
    #fimal .text-orange
    {
        text-transform: uppercase;
    }

    #final .text-orange span
    {
        text-transform: unset;
    }


    #final .text-orange
    {
        padding: 40px 50px;
        padding-top: 65px;
        border: 1px solid #FFFFFF;
        box-sizing: border-box;
        border-radius: 3px;
        font-size: 25px;
        line-height: 35px;
        font-weight: bold;
        max-width: 480px;
    }

    #final .questions-wrapper .text-mini
    {
        font-size: 25px;
        line-height: 35px;
        padding: 25px 0;
    }

    #final .button
    {
        height: 80px;
        width: 400px;
        font-size: 20px;
        line-height: 23px;
        background: linear-gradient(90deg, rgba(76, 217, 100, 0.9) -6.2%, rgba(50, 185, 73, 0.9) 100%);
        border-radius: 50px;
    }

    #final .text-mini:nth-child(1)
    {
        font-size: 25px;
        line-height: 35px;
    }

    #final .text-mini:nth-child(2)
    {
        color: #FFFFFF;
        margin-bottom: 35px;
        font-size: 25px;
        line-height: 35px;
    }
    
    #final .terms
    {
        font-size: 12px;
        line-height: 18px;
        color: #9D9D9D;
        letter-spacing: 3px;
    }
</style>

<script>
export default {
    data() {
        return {
            date: null
        }
    },

    created() {
        const date = new Date(new Date()).getDate() + 1;
        const month = new Date(new Date()).getMonth();
        const year = new Date(new Date()).getFullYear();
        this.date = `${date}.${month}.${year}`;
    }
}
</script>
