<template>
    <div class="wrap">
        <div class="todo">
            <input type="text"
                   v-on:keyup.enter = "addTodo"
                   placeholder="please write you todo"
            >
        </div>
        <item
                v-for="todo in todos"
                :key="todo.id"
                :todo="todo"
                @del="deleteItem"
        />
        <tab></tab>
    </div>

</template>
<script>
    import item from './list.vue';
    import tab from './tab.vue';
    let id = 0;
    export default {
        name: 'todo',
        data(){
            return {
                todos: [],
            }
        },
        computed: {

        },
        methods: {
            addTodo (e) {
                this.todos.unshift({
                    id: id++,
                    content: e.target.value.trim(),
                    completed: false
                });

                e.target.value = ' ';
            },
            deleteItem(id){
                this.todos.splice(this.todos.findIndex(todo => todo.id === id),1)
            }

        },
        components:{
            item,
            tab
        }
    }

</script>
<style scoped lang="less">
    .wrap {
        width: 450px;
        min-height: 600px;
        margin: 50px auto;
        background-color: lightpink;
        background-color: rgba(132,88,142,1);
        .todo {
            padding: 30px 60px;
            input {
                width: 300px;
                height: 30px;
                font-size: 18px;
            }
        }
    }

</style>