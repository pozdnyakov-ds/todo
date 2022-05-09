<template>
    <div style="margin: 5px 0 5px 0; padding: 5px; border-bottom: 1px solid #ccc;">
        <table style="width: 100%;"><tr>
            <td><a :class="className" href="#" @click="clickItem">{{ item.title }}</a></td>
            <td style="width: 10%;">
                <button @click="deleteItem">
                    <font-awesome-icon icon="trash" style="color: #666;"/>
                </button>
            </td>
        </tr></table>
    </div>
</template>

<script>
    export default {
        props: ['id', 'item', 'active'],
        emits: ['clickItem', 'deleteItem'],
        data() {
            return {
            }
        },
        methods: {
            clickItem() {
                this.$emit('clickItem', this.item.id)
            },
            deleteItem() {
                this.$emit('deleteItem', this.item.id)
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