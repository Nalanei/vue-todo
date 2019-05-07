<template>
    <div class="tab">
        <ul v-for="(item,key) in state" :key="key">
            <li><input type="radio" name="select"> {{item}}</li>
        </ul>
    </div>
</template>
<script>
    export default {
        name: "tab",
        data (){
            return {
                state: ['items','computed','delete']
            }
        }

    }
</script>
<style lang="less" scoped>
    .tab{
        margin-top: 200px;
        padding: 20px;
        ul {
            list-style: none;
            li {
                padding: 0 15px;
                display: inline-block;
                float: left;
            }
        }
    }
</style>