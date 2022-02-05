<template>
  <div class="container">
      <h1>О нас</h1>
      <p v-if="aboutContent">{{aboutContent.text}}</p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "about",
    data() {
      return {
          aboutContent:null
      }
    },
    async created() {
        await axios.get('https://demo-api.vsdev.space/api/farm/about_page').then(response => this.aboutContent = response.data);
    }
}
</script>

<style scoped>

</style>
