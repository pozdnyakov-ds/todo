<template>
<div style="width: 100%; background-color: #eee; padding: 10px;">
    <div style="width: 40%; padding: 10px; vertical-align: top;
        border: 1px solid #ccc; border-radius: 5px; text-align: left;
        background-color: white; display: inline-block;">
        <div style="margin-bottom: 20px;"><b>Заполнить данные:</b></div>
        <form @submit.prevent="submit">
            <div class="form-control">
                <label for="title">Заголовок</label>
                <input v-model.trim="title" type="text" id="title" placeholder="Введите заголовок">
            </div>
            <div class="form-control">
                <label for="textBody">Полный текст</label>
                <input v-model="textBody" type="textarea" style="height: 100px; overflow: auto;" id="textBody" placeholder="Текст статьи...">
            </div>
            <div class="form-control" style="margin-bottom: 20px;">
                <label for="status">Статус</label>
                <select v-model.number="status" id="status">
                    <option value="0">Черновик</option>
                    <option value="1">Новый</option>
                    <option value="2">Опубликован</option>
                    <option value="3">Скрыть</option>
                </select>
            </div>
            <button type="submit" class="btn primary" :disabled="title.length == 0">Отправить</button>
        </form>
    </div>
</div>    
</template>

<script>
    export default {
        data() {
            return {
                title: '',
                textBody: '',
                status: 0
            }
        },
        methods: {
            async submit() {
                // https://todo-77cd5-default-rtdb.europe-west1.firebasedatabase.app/users.json
                const res = await fetch('https://todo-77cd5-default-rtdb.europe-west1.firebasedatabase.app/articles.json', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'applications/json'
                    },
                    body: JSON.stringify({
                        title: this.title,
                        textBody: this.textBody,
                        status: this.status
                    })
                })
                const fbData = await res;
                console.log('fbData: ', fbData)

                this.title = ''
                this.textBody = ''
                this.status = 0

                this.$emit('loadArticles')
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>