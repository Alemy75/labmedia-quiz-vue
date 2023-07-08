<script>
export default {
  props: {
    
  },
}
</script>

<template>
  <header class="header">
    <div class="wrapper">
      <button class="header-button header-button__button">
        <div>
          <div class="line line_red"></div>
        </div>
        <div>
          <div class="line line_red"></div>
          <div class="line line_green"></div>
        </div>
        <div><div class="line line_green"></div></div>
      </button>
      Табы
    </div>
    <div class="lines header__lines">
      <span class="line line_thin line_red"></span>

      <span class="line line_thin line_green"></span>
    </div>
    <div
      class="line line_red line_thick line_progress"
      style="width: 386px"
    ></div>
  </header>
</template>

<style scoped></style>
