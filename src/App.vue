<script>
import Header from './components/blocks/Header.vue'
import Start from './components/slides/Start.vue'
import Questions from './components/slides/Questions.vue'
import Finished from './components/slides/Finished.vue'

export default {
  components: {
    Header,
    Start,
    Questions,
    Finished,
  },
  data() {
    return {
      status: 'start',
      score: 0,
      current: 0,
      questions: [
        {
          id: 1,
          title: 'Какие животные относятся к семейству кошачьих?',
          right: 1,
          answers: [
            {
              id: 1,
              title: 'Львы',
            },
            {
              id: 2,
              title: 'Собаки',
            },
            {
              id: 3,
              title: 'Кошки',
            },
          ],
        },
        {
          id: 2,
          title: 'Какое животное считается самым большим на Земле?',
          right: 1,
          answers: [
            {
              id: 1,
              title: 'Синий кит',
            },
            {
              id: 2,
              title: 'Слон',
            },
            {
              id: 3,
              title: 'Жираф',
            },
          ],
        },
        {
          id: 3,
          title: 'Какой вид животных относится к группе приматов?',
          right: 1,
          answers: [
            {
              id: 1,
              title: 'Обезьяны',
            },
            {
              id: 2,
              title: 'Львы',
            },
            {
              id: 3,
              title: 'Крокодилы',
            },
          ],
        },
        {
          id: 4,
          title: 'Какой животный вид является наиболее умным?',
          right: 1,
          answers: [
            {
              id: 1,
              title: 'Делфины',
            },
            {
              id: 2,
              title: 'Слоны',
            },
            {
              id: 3,
              title: 'Гепарды',
            },
          ],
        },
        {
          id: 5,
          title: 'Какое животное обладает самым длительным периодом сна?',
          right: 1,
          answers: [
            {
              id: 1,
              title: 'Летучая мышь',
            },
            {
              id: 2,
              title: 'Гепард',
            },
            {
              id: 3,
              title: 'Слон',
            },
          ],
        },
        {
          id: 6,
          title:
            'Как называется процесс превращения лягушки из полностью водного создания в земноводное?',
          right: 1,
          answers: [
            {
              id: 1,
              title: 'Метаморфоз',
            },
            {
              id: 2,
              title: 'Трансформация',
            },
            {
              id: 3,
              title: 'Мутация',
            },
          ],
        },
        {
          id: 7,
          title: 'Какие животные являются носителями вируса бешенства?',
          right: 1,
          answers: [
            {
              id: 1,
              title: 'Лисы',
            },
            {
              id: 2,
              title: 'Волки',
            },
            {
              id: 3,
              title: 'Медведи',
            },
          ],
        },
        {
          id: 8,
          title: 'Какой животный вид обладает самой длинной шеей?',
          right: 1,
          answers: [
            {
              id: 1,
              title: 'Жираф',
            },
            {
              id: 2,
              title: 'Слон',
            },
            {
              id: 3,
              title: 'Крокодил',
            },
          ],
        },
        {
          id: 9,
          title: 'Какие животные обладают способностью эхолокации?',
          right: 1,
          answers: [
            {
              id: 1,
              title: 'Летучие мыши',
            },
            {
              id: 2,
              title: 'Киты',
            },
            {
              id: 3,
              title: 'Зебры',
            },
          ],
        },
        {
          id: 10,
          title: 'Какое животное считается самым быстрым на суше?',
          right: 1,
          answers: [
            {
              id: 1,
              title: 'Гепард',
            },
            {
              id: 2,
              title: 'Лев',
            },
            {
              id: 3,
              title: 'Волк',
            },
          ],
        },
      ],
    }
  },
  computed: {},
  methods: {
    setStatus(value) {
      return (this.status = value)
    },
    setScore() {
      this.score++
    },
    setCurrent() {
      this.current++
    },
    clearScore() {
      this.score = 0
      this.current = 0
    },
  },
}
</script>

<template>
  <Header />
  <section class="content">
    <Start v-if="status === 'start'" :setStatus="setStatus" />

    <Questions
      v-if="status === 'answering'"
      :setStatus="setStatus"
      :questions="questions"
      :current="current"
      :setCurrent="setCurrent"
      :setScore="setScore"
    />

    <Finished
      v-if="status === 'finished'"
      :setStatus="setStatus"
      :score="score"
      :clearScore="clearScore"
    />

    <div class="lines content__lines">
      <span class="line line_thick line_red"></span>
      <span class="line line_thick line_green"></span>
    </div>
  </section>
</template>

<style scoped></style>
