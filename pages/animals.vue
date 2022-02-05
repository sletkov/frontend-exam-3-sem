<template>
    <div>
        <h1>Животные</h1>
        <button class="btn btn-primary" @click="isFormVisible = !isFormVisible">Открыть форму</button>
        <form action="" v-if="isFormVisible">
            <div class="mb-3">
                <label  class="form-label">Тип животного</label>
                <select class="form-control form-select form-select-lg mb-3" aria-label=".form-select-lg example">
                    <option v-model="currentAnimalType">Корова</option>
                    <option v-model="currentAnimalType">Кролик</option>
                    <option v-model="currentAnimalType">Овца</option>
                </select>
            </div>
            <div class="mb-3">
                <label  class="form-label">Укажите количество животных</label>
                <input v-model="currentAnimalCount" type="number" class="form-control" id="exampleFormControlInput1" placeholder="Количество животных" :min="1">
            </div>
            <button  type="button" class="btn btn-primary" @click="addAnimals(currentAnimalType, currentAnimalCount)">Добавить</button>
        </form>
        <div class="row">
            <div class="col-md-6 mt-4">
                <img src="../static/cow_img.jpg" alt="">
                <p>Всего коров: </p>
            </div>

            <div  class="col-md-6 mt-4">
                <img src="../static/rabbit_img.jpg" alt="">
                <p>Всего кроликов: </p>
            </div>

            <div class="col-md-6 mt-4">
                <img  src="../static/sheep_img.jpg" alt="">
                <p>Всего овец: </p>
            </div>

        </div>
    </div>
</template>

<script>

function Animal(animalType,count) {
    this.animalType = animalType;
    this.count = count
}

export default {
    name: "animals",
    layout: 'default',
    head: {
        title: 'Animals'
    },
    data() {
        return {
            currentAnimalType : 'sheeps',
            currentAnimalCount : 0,
            isFormVisible: false,

        }
    },
}
</script>

<style scoped>
    .unvisible {
        display: none;
    }
</style>
