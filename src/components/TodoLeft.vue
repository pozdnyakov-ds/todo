<template>
    <div style="width: 25%; background-color: #fff; display: inline-block; 
        padding: 10px; border-right: 1px solid #ccc; height: 90vh;"
    >
    <div style="margin-bottom: 20px;"><b>МЕНЮ</b></div>
    <TodoItem 
        v-for="(item, index) in items"
        :key="index"    
        :item="item"
        :active="active"
        @clickItem="clickItem"
        @deleteItem="deleteItem"
    ></TodoItem>
    <div v-if="items.length == 0">Нет данных</div>
    </div>
</template>

<script>
    import TodoItem from '../components/TodoItem.vue'
    export default {
        props: ['items', 'active'],
        emits: ['clickItem', 'deleteItem'],
        methods: {
            clickItem(id) {
                this.$emit('clickItem', id)
            },
            deleteItem(id) {
                this.$emit('deleteItem', id)
            }
        },
        components: {
            TodoItem
        }
    }
</script>

<style scoped>

</style>