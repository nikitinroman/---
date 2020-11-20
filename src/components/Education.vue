<template>
  <div class="bigDiv">
    <div class="contentDiv">
      <a name="education"></a>
      <h1 style="text-align: center; color: darkgrey">Образование</h1>
      <div class="miniContentDiv">
        <div class="miniContentDivItems">
          <div class="divWithItems">
            <div @click="divClick(item.id)" class="divItems" v-for="item in listOfCourses" v-bind:key="item.id">
              <div class="content">{{item.title}}</div>
            </div>
          </div>
        </div>
        <div style="border-left: 1px solid black; margin: 70px 0px;"></div>
        <div class="miniContentDivItems">
          <div class="flyingDiv">
            <div>
              <p v-if="choosed == -1">Выберите курс из списка слева, чтобы узнать, чему я научился!</p>
              <div v-else>
                <p style="font-size: larger">{{listOfCourses[choosed].content}}</p>
                <a :href="listOfCourses[choosed].url">Ссылка на курс</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Education',
  data(){
  return{
    choosed: -1,
    listOfCourses: [
      {
        id: 0,
        title: 'Степик Основы статистики',
        content: 'Данный курс дал мне знания о статистике в целом- я узнал, что такое гипотезы и методы их принятия, впервые услышал о применении математики в реальной жизни. Узнал про А/Б тесты.',
        url: 'https://stepik.org/course/76/syllabus',
      },
      {
        id: 1,
        title: 'Степик Введение в Data Science и машинное обучение',
        content: 'В данном курсе я начал свое ознакомление с библиотеками Pandas и Sklearn, очистил, обработал, визуализировал свой первый датасет. Фитанул свои первые модельки и начал познавать основы машнного обучения.',
        url: 'https://stepik.org/course/4852/syllabus',
      },
      {
        id: 2,
        title: 'Computer science center Data Science / Анализ данных',
        content: 'В данном курсе я закрепил и расширил кругозор своих знаний в области науки о данных, больше узнал про разные технологии МО- такие, как RandomForest, XGBoost.',
        url: 'https://compscicenter.ru/syllabus/on-campus/ds/',
      },
      {
        id: 3,
        title: 'Netology аналитик данных',
        content: 'Данный курс я просмотрел достаточно бегло, закрепил свои знания в SQL, прослушал несколько кейсов, в которых так или иначе была применена технология МО.',
        url: 'https://netology.ru/programs/data-analyst',
      },
      {
        id: 4,
        title: 'Фреймворк Vue.JS. Полное руководство для современной веб-разработки',
        content: 'Данный курс немного выбивается из общей тематики моего дополнительного образования- но мне стало интересно, что из себя представляет фронтенд разработка, захотелось делать что-то красивое, видеть результат своих трудов "здесь и сейчас". Изучил Html, css, js и фреймворк Vue',
        url: 'https://ibrain.ru/freymvork-vue-js-polnoe-rukovodstvo-dlya-sovremennoy-veb-razrabotki/',
      },
    ],
  }
  },
  methods:{
    divClick(id){
      this.choosed = id
    }
  }
}
</script>

<style scoped>
.bigDiv{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-color: white;
  padding-top: 10px;
}
.contentDiv{
  width: 80%;
  height: 80%;
  border: 2px solid black;
  color: whitesmoke;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0,0,0,0.5);
  background: url("https://www.happymigration.com/wp-content/uploads/2019/01/326.jpg") 50% 50% no-repeat;
}
.miniContentDiv{
  display: flex;
  justify-content: space-around;
}
.miniContentDivItems{
  border: 1px solid black;
  height: 500px;
  width: 37%;
  border-radius: 5px;
  text-align: center;
  padding: 0 20px;
}
.divWithItems{
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 25px;
}
.divItems{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 80%;
  height: 80px;
  border: 1px solid black;
  margin-bottom: 5px;
  border-radius: 5px;
}
.divItems:hover{
  border: 1.5px solid black;
  background-color: darkgrey;
  opacity: 0.5;
}
.divItems:hover .content{
  color: black;
}
a{
  text-decoration: none;
  color: darkgrey;
  font-weight: bold;
  font-size: larger;
}
.flyingDiv{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100%;
}
</style>
