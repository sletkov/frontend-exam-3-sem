<template>
    <div>
        <h1>Животные</h1>
        <button class="btn btn-primary" @click="isFormVisible = !isFormVisible">Открыть форму</button>
        <Form v-if="isFormVisible"/>
        <div class="row" v-if="animals">
            <div class="col-md-6" v-for="(animal,index) in animals" :key="index">
                <h2>{{animal.name}}</h2>
                <img v-if="animal.type === 'cow'" src="cow_img.jpg">
                <img v-if="animal.type === 'rabbit'" src="rabbit_img.jpg">
                <img v-if="animal.type === 'sheep'" src="sheep_img.jpg">
                <p><b>Вес: </b>{{ animal.weight }} кг</p>
                <p><b>Цвет: </b>{{ animal.color }}</p>
                <p><b>Пол: </b>{{ animal.sex }}</p>
            </div>
        </div>
    </div>
</template>

<script>

import axios from "axios";

export default {
    name: "animals",
    layout: 'default',
    head: {
        title: 'Animals'
    },
    data() {
        return {
            isFormVisible: false,
            animals: null
        }
    },
    async created() {
        await axios.get('https://demo-api.vsdev.space/api/farm/baby').then(response => this.animals = response.data);
    }

}
</script>

<style scoped>
    .unvisible {
        display: none;
    }
</style>
