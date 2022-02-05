<template>
  <aside class="container">
      <b>В нашем роддоме родилось:</b>
      <p>Добрейших коровок: {{ widgetInfo.cows }}</p>
      <p>Милейших кроликов: {{ widgetInfo.rabbits }}</p>
      <p>Пушистых овечек: {{ widgetInfo.sheeps }}</p>
  </aside>
</template>

<script>
import axios from 'axios'

export default {
    name: "sidebar",
    data() {
        return {
            widgetInfo: null,
        }
    },
    created() {
        axios.get('https://demo-api.vsdev.space/api/farm/left_widget').then(response => this.widgetInfo = response.data);
    }

}


</script>

<style scoped>
</style>
