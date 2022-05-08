<template>
    <div style="width: 25%; background-color: #fff; display: inline-block; 
        padding: 10px; border-right: 1px solid #ccc; height: 90vh;"
    >
    <div><b>МЕНЮ</b></div>
    <TodoItem 
        v-for="(item, index) in items"
        :key="index"    
        :item="item"
        @clickItem="clickItem"
    ></TodoItem>
    </div>
</template>

<script>
    import TodoItem from '../components/TodoItem.vue'
    export default {
        props: ['items'],
        data() {
            return {
                selectedId: 'Не выбран'
            }
        },
        methods: {
            clickItem(id) {
                //console.log('Letf ID', id)
                this.$emit('clickItem', id)
            }
        },
        components: {
            TodoItem
        }
    }
</script>

<style>

</style>