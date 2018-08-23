<template>
  <div id="app">

    <section v-for="(subjects, day) in schedule" :key="day">

      <h1>{{ day }}</h1>
      <item v-for="(s, i) in subjects" :subject="s" :prev="subjects[i-1] || {}" :key="s.from"/>

    </section>

  </div>
</template>

<script>
import item from './components/item.vue'

export default {
  name: 'app',
  components: {
    item
  },
  data: () => ({
    schedule: {
      'Вторник': [
        {
          title: 'Виртуализация и виртуальные машины',
          from: '10:30',
          to: '11:50',
          who: 'Н. Иготти',
          type: 'лекция',
          place: 'ВШЭ',
        },
        {
          text: '3.5 часа'
        },
        {
          title: 'Программирование на Java',
          from: '15:20',
          to: '16:40',
          who: 'А.М.Кузнецов',
          type: 'лекция',
          place: '405',
          mark: 'blue',
        },
        {
          title: 'Компиляторы',
          from: '16:50',
          to: '18:10',
          who: 'Д.Ю.Булычев',
          type: 'лекция',
          place: 'ВШЭ',
        },
        {
          title: 'Компиляторы',
          from: '18:20',
          to: '19:40',
          who: 'Д.Ю.Булычев',
          type: 'практика',
          place: 'ВШЭ',
        },
      ],

      'Среда': [
        {
          title: 'Альтернативные\n языки для JVM',
          from: '10:30',
          to: '11:50',
          who: 'М.Зареченский',
          type: 'неясно',
          place: 'ВШЭ',
        },
        {
          title: 'Программирование с ЗТ',
          from: '12:10',
          to: '13:30',
          who: 'В.Исаев',
          type: 'лекция',
          place: '405',
          mark: 'blue',
        },
        {
          title: 'Программирование с ЗТ',
          from: '13:40',
          to: '15:00',
          who: 'В.Исаев',
          type: 'практика',
          place: '405',
          mark: 'blue',
        },
        {
          title: 'Метавычисления',
          from: '15:20',
          to: '16:40',
          who: 'Д.Березун',
          type: 'лекция',
          place: 'ВШЭ',
          mark: 'yellow',
        },
        {
          title: 'Метавычисления',
          from: '16:50',
          to: '18:10',
          who: 'Д.Березун',
          type: 'практика',
          place: 'ВШЭ',
          mark: 'yellow',
        },
      ],

      'Четверг': [
        {
          title: 'Графические интерфейсы',
          from: '16:50',
          to: '18:10',
          who: 'М.Брыксин',
          type: 'лекция',
          place: 'ВШЭ',
          mark: 'yellow',
        },
        {
          title: 'Графические интерфейсы',
          from: '18:20',
          to: '19:40',
          who: 'М.Брыксин',
          type: 'практика',
          place: 'ВШЭ',
          mark: 'yellow',
        },

      ],

      'Пятница': [
        {
          title: 'Программирование на Java',
          from: '12:10',
          to: '13:30',
          who: 'Д.Саввинов\nС.Прошев',
          type: 'практика',
          place: '404, 405',
          mark: 'blue',
        },
        {
          title: 'Высокопроизводительные вычисления',
          from: '13:40',
          to: '15:00',
          who: 'Е.Л.Калишенко',
          type: 'лекция',
          place: '405',
          mark: 'blue',
        },
        {
          title: 'Высокопроизводительные вычисления',
          from: '15:20',
          to: '16:40',
          who: 'Е.Л.Калишенко',
          type: 'практика',
          place: '405',
          mark: 'blue',
        },
        {
          title: 'Слушания дипломов',
          from: '16:50',
          to: '18:10',
          // who: '',
          type: 'пиздец',
          // place: 'неясно',
          mark: 'blue',
        }
      ]
    }
  })
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: inherit;
}

html, body {
  height: 100%;
  box-sizing: border-box;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #3c3c3c;
  margin-bottom: 60px;
}

h1 {
  margin: 2.5em 0 1em;
  font-family: 'Anonymous Pro', monospace;
  font-family: 'Alegreya SC', serif;
  /*font-family: 'Kurale', serif;*/
  /*font-family: 'Roboto Slab', serif;*/
  font-weight: 400;

}

section:first-of-type h1 {
  margin-top: 2em
}
</style>
