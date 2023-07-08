<script>
import Answers from '../blocks/Answers.vue'

export default {
  props: {
    questions: Array,
    setStatus: Function,
    setScore: Function,
    current: Number,
    setCurrent: Function
  },
  components: {
    Answers,
  },
  data() {
    return {
      
      enabled: false,
      checkedId: null,
    }
  },
  methods: {
    nextQuestonHandler() {
      if (this.enabled) {
        if (this.checkedId === this.questions[this.current].right) {
          this.setScore()
        }

        if (this.current < this.questions.length - 1) {
          this.setCurrent()
        } else {
          this.setStatus('finished')
        }

        this.enabled = false

        this.checkedId = null
      }
    },
    setRatio(id) {
      this.checkedId = id
      this.enabled = true
    },
  },
  computed: {
    buttonClassList() {
      if (this.enabled) {
        return 'button question__button'
      } else {
        return 'button question__button button_disabled'
      }
    },
  },
}
</script>

<template>
  <div class="question">
    <div class="wrapper wrapper_block">
      <h1>Тестирование</h1>
      <div class="content__wrapper">
        <p class="question__title">
          {{ questions[current].title }}
        </p>
      </div>

      <Answers
        :answers="questions[current].answers"
        :setStatus="setStatus"
        :setRatio="setRatio"
        :checkedId="checkedId"
      />

      <button
        :class="buttonClassList"
        :disabled="!enabled"
        @click="nextQuestonHandler"
      >
        Принять
      </button>
    </div>
  </div>
</template>

<style></style>
