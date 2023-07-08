<script>
export default {
  props: {
    setStatus: Function,
    clearScore: Function,
    score: Number
  },
  data() {},
  methods: {
    onClickHandler() {
      this.setStatus('start')
      this.clearScore()
    },
  },
}
</script>

<template>
  <div class="question">
    <div class="wrapper wrapper_block">
      <h1>Тестирование</h1>
      <div class="content__wrapper">
        <p class="question__title">Конец</p>
      </div>
      <button class="button" @click="onClickHandler">
        Пройти еще раз {{ score }}
      </button>
    </div>
  </div>
</template>

<style></style>
