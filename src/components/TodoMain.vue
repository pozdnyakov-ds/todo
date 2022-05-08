<template>
    <div v-if="items[id]" class="item">{{ items[id] }}</div>
    <div v-else class="item">Выбрать элемент</div>
</template>

<script>
    export default {
        props: ['id', 'items']
        
    }
</script>

<style>
    .item {
        margin: 5px; background-color: #fff; display: inline-block; 
        padding: 10px; vertical-align: top;
    }
</style>