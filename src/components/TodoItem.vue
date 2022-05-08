<template>
    <div style="margin: 5px 0 5px 0; padding: 5px; border-bottom: 1px solid #ccc;">
        <a :class="className" href="#" @click="clickItem">{{ item.title }}</a>
    </div>
</template>

<script>
    export default {
        props: ['id', 'item', 'active'],
        data() {
            return {
            }
        },
        methods: {
            clickItem() {
                this.$emit('click-item', this.item.id)
            }
        },
        computed: {
            className: function() {
                if (this.active == this.item.id) {
                    return 'todoLinkActive' 
                } else {
                    return 'todoLink'
                }
            }
        }
    }
</script>

<style scoped>
    .todoLink {
        text-decoration: none;
        font-weight: normal;
    }
    .todoLinkActive {
        text-decoration: none;
        font-weight: bold;
    }
</style>