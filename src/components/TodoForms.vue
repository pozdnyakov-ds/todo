<template>
<div style="width: 100%; background-color: #eee; padding: 10px;">
    <div style="width: 50%; padding: 10px; vertical-align: top;
        border: 1px solid #ccc; border-radius: 5px; text-align: left;
        background-color: white; display: inline-block;">
        <div style="margin-bottom: 20px;"><b>Заполнить данные:</b></div>
        <form @submit.prevent="submit">
            <div class="form-control">
                <label for="name">Имя</label>
                <input v-model.trim="name" type="text" id="name" placeholder="Введите имя">
            </div>
            <div class="form-control">
                <label for="age">Возраст</label>
                <input v-model.number="age" type="text" id="age" placeholder="Введите возраст">
            </div>
            <div class="form-control" style="margin-bottom: 20px;">
                <label for="city">Город</label>
                <select v-model="city" id="city">
                    <option value="msk">Москва</option>
                    <option value="kzn">Казань</option>
                </select>
            </div>
            <button type="submit" class="btn primary">Отправить</button>
        </form>
    </div>
    <div style="width: auto; padding: 10px; margin-left: 10px; vertical-align: top;
        border: 1px solid #ccc; border-radius: 5px; text-align: left;
        background-color: white; display: inline-block;">
        <TodoUserList></TodoUserList>
    </div>    
</div>    
</template>

<script>
    import TodoUserList from '../components/TodoUserList.vue'

    export default {
        data() {
            return {
                name: '',
                age: 25,
                city: ''
            }
        },
        methods: {
            submit() {
                console.info('Submit...')
                console.log(this.name, this.age, this.city)
            }
        },
        components: {TodoUserList}
    }
</script>

<style lang="scss" scoped>

</style>