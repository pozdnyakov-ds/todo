<template>
    <div style="margin: 5px 0 5px 0; padding: 5px; border-bottom: 1px solid #ccc;">
        <a class="menuItem" :class="className" href="#" @click="clickItem">{{ item.title }}</a>
    </div>
</template>

<script>
    export default {
        props: ['id', 'item'],
        data() {
            return {
                active: false
            }
        },
        methods: {
            clickItem() {
                // const elements = this.$el.querySelectorAll('menuItem')
                // console.log('All: ', elements)
                // for (let elem of elements) {
                //     console.log('El: ', elem)
                // }

                this.active = !this.active
                this.$emit('click-item', this.item.id)
            }
        },
        computed: {
            className: function() {
                if (this.active) {
                    return 'todoLinkActive' 
                } else {
                    return 'todoLink'
                }
            }
        }
    }
</script>

<style>
    .todoLink {
        text-decoration: none;
        font-weight: normal;
    }
    .todoLinkActive {
        text-decoration: none;
        font-weight: bold;
    }
</style>