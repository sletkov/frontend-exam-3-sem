<template>
    <form action="" v-if="formFields">
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

            },

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
        }
    }

}
</script>

<style scoped>

</style>
