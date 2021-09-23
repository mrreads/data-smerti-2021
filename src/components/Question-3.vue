<template>
    <div id="test">
        <div class="container">

            <p class="text-magic"> Уже совсем скоро Вы узнаете много <br> интересного о своем будущем! </p>
            <hr>

            <div class="questions-wrapper">
                <p class="text-orange">УКАЖИТЕ СВОЮ ДАТУ <br> РОЖДЕНИЯ</p>
                
                <div class="select-wrapper">
                    <div class="select" @click="expandDay = true" ref="eDay"> {{ selectedDay }} </div>
                    <div class="select-dropdown" v-if="expandDay">
                        <p v-for="index in 31" :key="index" @click="selectedDay = index, expandDay = false; check()"> {{ index }}</p>
                    </div>
                </div>


                <div class="select-wrapper">
                    <div class="select" @click="expandMonth = true" ref="eMonth"> {{ selectedMonth }} </div>
                    <div class="select-dropdown" v-if="expandMonth">
                        <p v-for="index in 12" :key="index" @click="selectedMonth = index, expandMonth = false; check()"> {{ index }}</p>
                    </div>
                </div>

                <div class="select-wrapper">
                    <div class="select" @click="expandYear = true" ref="eYear"> {{ selectedYear }} </div>
                    <div class="select-dropdown" v-if="expandYear">
                        <p v-for="(index) in yearRange(1900, 2002)" :key="index" @click="selectedYear = index, expandYear = false; check()"> {{ index }}</p>
                    </div>
                </div>


                <button class="button blick" @click="goNext"> Далее </button>
            </div>


            <p class="text-mini test-count">Вопрос 3-5</p>
        </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            expandDay: false,
            expandMonth: false,
            expandYear: false,

            selectedDay: "День",
            selectedMonth: "Месяц",
            selectedYear: "Год"
        }
    },
    methods: {
        goNext()
        {
            this.check();

            if (this.selectedDay != 'День' &&
                this.selectedMonth != 'Месяц' &&
                this.selectedYear != 'Год')
                {
                    const temp = new Date(this.selectedYear, this.selectedMonth, this.selectedDay);
                    const current = new Date();
                    const age = current.getFullYear() - temp.getFullYear();

                    this.$parent.userAge = age;
                    this.$parent.currentQuestion++

                }
        },
        check()
        {
            if (this.selectedDay == 'День')
                this.$refs['eDay'].classList.add('error');
            else
                this.$refs['eDay'].classList.remove('error');

            if (this.selectedMonth == 'Месяц')
                this.$refs['eMonth'].classList.add('error');
            else
                this.$refs['eMonth'].classList.remove('error');

            if (this.selectedYear == 'Год')
                this.$refs['eYear'].classList.add('error');
            else
                this.$refs['eYear'].classList.remove('error');
        },
        yearRange(start,stop)
        {
            return new Array(stop-start + 1).fill(start).map((n,i)=>n+i).reverse();
        }
    }
}
</script>
