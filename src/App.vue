<template>
    <div id="app">
        {{msg}}
        <div>
            <input type="text" v-model="info">
            <button v-on:click="handleClick">添加</button>
        </div>
        <ul>
            <todo-item v-for="item in list" v-bind:key="item">
                <template v-slot:slot_item="itemProps">
                    <span v-bind:style="{fontSize: '20px', color: itemProps.checked ? 'red': 'blue'}">{{item}}</span>
                </template>
            </todo-item>
        </ul>
    </div>
</template>

<script>
    import TodoItem from "./components/TodoItem";

    export default {
        name: 'App',
        components: {
            TodoItem
        },
        data() {
            return {
                msg: "Hello ZhangFuWei",
                info: "",
                list: []
            }
        },
        methods: {
            handleClick() {
                this.list.push(this.info)
                this.info = ""
            }
        }
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
