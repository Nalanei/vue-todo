<template>
   <div :class="['todolist', todo.completed ? 'completed' : '']">
       <input type="checkbox" v-model="todo.completed">
       <label>{{todo.content}}</label>
       <button v-on:click="del">删除</button>
   </div>
</template>
<script>
    export default {
        name: 'list',
        props: {
            todo: {
                type: Object,
                required: true
            }
        },
        data (){
            return {

            }
        },
        methods:{
            del() {
                this.$emit('del',this.todo.id)
            }
        }
    }

</script>
<style lang="less" scoped>
    .completed{
        text-decoration: line-through;
    }
    .todolist {
        padding: 5px 90px 5px 55px;
        font-size: 20px;
        input {
            width: 20px;
            height: 20px;
        }
        button {
            width: 50px;
            height: 25px;
            line-height: 25px;
            text-align: center;
            float: right;
            border: none ;
            outline: none;
            border-radius: 5px;
            cursor: pointer;
        }

    }
</style>