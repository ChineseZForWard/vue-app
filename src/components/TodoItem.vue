<template>
    <li class="theItem">
        <input type="checkbox" v-model="checked">
        <slot name="slot-item" v-bind="{checked}"></slot>
    </li>
</template>

<script>
    export default {
        name: "TodoItem",
        props: ['the_item'],
        data() {
            return {
                checked: false
            }
        }
    }
</script>

<style scoped>
    .theItem {
        color: red;
    }
</style>
