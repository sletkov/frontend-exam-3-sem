<template>
  <div class="container">
      <h1>Фермерский роддом номер 5</h1>

      <div class="row" v-if="homeContent">
        <img class="col-md-6" :src="homeContent.image" alt="">
          <p class="col-md-6">{{ homeContent.text }}</p>
    </div>
  </div>

</template>

<script>
import axios from "axios";

export default {
    name: "index",
    layout: 'default',
    head: {
        title: 'Homepage'
    },
    data() {
        return {
            homeContent : null
        }
    },
    async created() {
        await axios.get('https://demo-api.vsdev.space/api/farm/home_page').then(response => this.homeContent = response.data);
    }

}
</script>

<style scoped>

</style>
