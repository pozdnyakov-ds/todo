<template>
    <div style="width: 25%; background-color: #fff; display: inline-block; 
        padding: 10px; border-right: 1px solid #ccc; height: 90vh;"
    ><b>МЕНЮ</b>
    <TodoItem 
        v-for="item in items"
        :key="item"    
        :item="item"
    ></TodoItem>
    </div>
</template>

<script>
    import TodoItem from '../components/TodoItem.vue'
    export default {
        props: ['items'],
        data() {
            return {

            }
        },
        components: {
            TodoItem
        }
    }
</script>

<style lang="scss" scoped>

</style>