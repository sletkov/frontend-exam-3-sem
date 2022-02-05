<template>
  <div class="container">
      <h1>Фермерский роддом номер 5</h1>
      <div class="row">
<!--        <img class="col-md-6" :src="content.image" alt="">-->
<!--          <p>{{ content.text }}</p>{-->
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
            content : null
        }
    },
    // created() {
    //     axios.get('https://demo-api.vsdev.space/api/farm/home_page').then(response => this.content = response.data);
    // }

}
</script>

<style scoped>

</style>
