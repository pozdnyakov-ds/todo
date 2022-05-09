<template>
    <div v-if="active !== 0" class="item">
        <div v-for="(item, index) in items" :key="index">
            {{(item.id == active) ? item : null}}
        </div>
    </div>
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