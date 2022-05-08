<template>
    <div v-if="items[active]" class="item">{{ items[active] }}</div>
    <div v-else class="item">Выбрать элемент</div>
</template>

<script>
    export default {
        props: ['active', 'items'],
    }
</script>

<style scoped>
    .item {
        margin: 5px; background-color: #fff; display: inline-block; 
        padding: 10px; vertical-align: top;
    }
</style>