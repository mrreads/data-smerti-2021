<template>

  <div class="section_one" data-aos="zoom-out-up">
    <div class="container">
      <p class="text-mini">Лучшие астрологи и экстрасенсы Румынии</p>
      <hr>
      <p class="text-large">Точность прогноза: 97%</p>

      <div class="border-wrapper">
        <img class="image" src="./../assets/img/section1_image.png" alt="Девушка">
        <img class="border" src="./../assets/img/section1_border.png" alt="Рамка">
      </div>
      <p class="text-orange">Вас беспокоит вопрос о том, <br> КОГДА ВЫ ПОКИНИТЕ ЭТОТ МИР И ПРИ <br> КАКИХ ОБСТОЯТЕЛЬСТВАХ? </p>
      
      <p class="button blick" @click="scrollTo('scroll_question')"> Да </p>
      <p class="button blick" @click="scrollTo('scroll_question')"> Нет </p>

      <p class="text-mini">Онлайн предсказание</p>
    </div>
  </div>

  <div class="section_two" data-aos="fade-up" data-aos-duration="2000">
    <div class="container">
      <div class="border">
        <img class="image" src="./../assets/img/section2_image.png" alt="Руки">
          <p>Позвольте нам раскрыть эту <br> 
          волнующую тайну и <br>
          <span>с точностью определить дату <br>
          и время вашей смерти, </span>а <br>
          также предшествующую <br>
          этому событию причину </p>
      </div>
    </div>
  </div>

  <div class="section_three" data-aos="fade-up" data-aos-duration="3000">
    <div class="container">
      <p>Многие не верят <br>
      предсказаниям и мы решили <br>
      доказать каждому, <br>
      <span> что прогноз может изменить <br>
       жизнь любого человека! </span></p>
    </div>
  </div>

  <div ref="scroll_question" class="section_four" data-aos="zoom-out-up">
    <div class="container">
      <p class="text-orange">БОИТЕСЬ ЛИ ВЫ УМЕРЕТЬ?</p>
      
      <router-link to="/test" class="button blick"> Да</router-link>
      <router-link to="/test" class="button blick"> Нет </router-link>

      <p class="text-mini">Вопрос 1-5</p>
    </div>
  </div>

  <div  class="section_five" data-aos="zoom-out-up">
    <div class="container">
      <img class="rune" src="./../assets/img/rune1.svg" alt="Руна">
      <p class="text-magic">
        Вы, конечно, умрете. <br> 
        И все, с кем вы знакомы, <br> 
        тоже однажды умрут. </p>
      <img class="rune"  src="./../assets/img/rune2.svg" alt="Руна">
    </div>
    <p class="terms" @click="changeFooterVisible">TERMENI SI CONDITII: ACESTA ESTE UN SERVICIU DE DIVERTISMENT. PRIN FOLOSIREA LUI DECLARATI CA AVETI 18 ANI IMPLINITI. </p>
    <p class="terms" data-aos="zoom-out-up" v-if="showFooter" @click="changeFooterVisible">TERMENI SI CONDITII: ACESTA ESTE UN SERVICIU DE DIVERTISMENT. PRIN FOLOSIREA LUI DECLARATI CA AVETI 18 ANI IMPLINITI, TERMENI SI CONDITII: ACESTA ESTE UN SERVICIU DE DIVERTISMENT. PRIN FOLOSIREA LUI DECLARATI CA AVETI 18 ANI IMPLINITI, TERMENI SI CONDITII: ACESTA ESTE UN SERVICIU DE DIVERTISMENT. PRIN FOLOSIREA LUI DECLARATI CA AVETI 18 ANI IMPLINITI. </p>
  </div>
  
</template>

<script>
export default {
  name: 'App',
  
  data() {
    return {
      showFooter: false
    }
  },

  mounted() {
    document.title = 'Дата смерти 2021';
  },

  methods: {
    scrollTo(id) { this.$refs[id].scrollIntoView() },
    changeFooterVisible() { this.showFooter = !this.showFooter; }
  }
}
</script>
