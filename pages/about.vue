<template>
  <div class="container">
      <h1>О нас</h1>
        <p>{{content.text}}</p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "about",
    data() {
      return {
          content:null
      }
    },
    created() {
        axios.get('https://demo-api.vsdev.space/api/farm/about_page').then(response => this.content = response.data);
    }
}
</script>

<style scoped>

</style>
