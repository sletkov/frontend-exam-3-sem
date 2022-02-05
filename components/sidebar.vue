<template>
  <aside class="container" v-if="widgetInfo">
<!--      <b>Левый виджет-->
<!--          В нашем роддоме ежедневно рождаются десятки милейших зверушек-->
<!--      </b>-->
<!--      <img src="left_widget_img.jpg" alt="">-->
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
    async created() {
        await axios.get('https://demo-api.vsdev.space/api/farm/left_widget').then(response => this.widgetInfo = response.data);
    }

}


</script>

<style scoped>
</style>
