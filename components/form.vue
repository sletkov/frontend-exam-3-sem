<template>
    <form action="" v-if="formFields" @submit="checkForm">
        <p v-if="errors.length" class="text-danger">
            <b>Пожалуйста исправьте указанные ошибки:</b>
        <ul>
            <li v-for="error in errors">{{ error }}</li>
        </ul>
        </p>

        <div v-for="(field, index) in formFields" :key="index" class="form-group">
            <label class="form-label">{{field.title}}</label>
            <input  v-model="postData[index]" v-if="field.type === 'string'" type="text" class="form-control">
            <select  v-model="postData[index]" v-else  class="form-control form-select form-select-lg mb-3">
                <option :value="value" v-for="(value,index) in field.values " :key="index">
                    {{value}}
                </option>
            </select>

        </div>
        <button  type="submit" class="btn btn-primary" @click="addAnimal()">Добавить</button>

    </form>
</template>

<script>
import axios from "axios";
export default {
    name: "Form",
    data() {
        return {
            formFields: null,
            postData: {
                type: '',
                name: '',
                weight: '',
                color: '',
                sex: '',
            },
            errors: []
        }
    },

    async created() {
            await axios.get('https://demo-api.vsdev.space/api/farm/baby/form').then(response => this.formFields = response.data.fields);
    },
    methods: {
        async addAnimal() {
            console.log(this.postData);
            try {
                await axios.post('https://demo-api.vsdev.space/api/farm/baby',Object.assign(this.postData)).then(response => console.log(response));
            } catch(e){
                console.log(e);
            }
        },
        checkForm: function (e) {
            if (this.name && this.age) {
                return true;
            }

            this.errors = [];

            if (!this.postData.type) {
                this.errors.push('Требуется указать тип животного.');
            }
            if (!this.postData.name) {
                this.errors.push('Требуется указать имя животного.');
            }
            if (!this.postData.weight) {
                this.errors.push('Требуется указать вес животного.');
            }
            if (!this.postData.color) {
                this.errors.push('Требуется указать цвет животного.');
            }
            if (!this.postData.sex  ) {
                this.errors.push('Требуется указать пол животного.');
            }

        }
    }

}
</script>

<style scoped>

</style>
