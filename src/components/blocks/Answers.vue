<script>
export default {
  props: {
    answers: Array,
    setStatus: Function,
    setRatio: Function,
    checkedId: Number | null,
  },
  data() {
    return {
      
    }
  },
  methods: {
    checkedStatus(id) {
        if (this.checkedId == id) {
          return true
        } else {
          return false
        }
      },
  },
  computed: {
    shuffleAnswers() {
        return this.answers.sort(() => Math.random() - 0.5);
    }
  },
}
</script>

<template>
  <ul class="question__answers">
    <li v-for="item in shuffleAnswers" :key="item.id">
      <div class="control-group">
        <label class="control control-radio">
          {{ item.title }}
          <input
            type="radio"
            name="radio"
            @change="setRatio(item.id)"
            :checked="checkedStatus(item.id)"
          />
          <div class="control_indicator"></div>
        </label>
      </div>
    </li>
  </ul>
</template>
