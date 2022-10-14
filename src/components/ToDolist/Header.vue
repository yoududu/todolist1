<template>
    <header class="todolist-header">
        <div class="todolist-container todolist-header-container">
        <h1 class="todo-title">ToDoList</h1>
        <input type="text" class="todo-serach" placeholder="添加toDo" v-model="search" @keydown.enter="inputadd"><!--@keydown.enter输入键盘事件，回车-->
    </div>
    </header>
</template>
<script>
export default{
    name:"ToDoHeader",
    data(){
        return{
            id:0,
            search:""
        }
    },
    methods:{
       inputadd(){
        if(this.search){ //非空验证
            // console.log(11)
        this.$emit("addtodo",{
            id:this.id++,
            content:this.search
        })
        this.search = ""; //enter完清空输入框
        }
        
       } 
    }
}</script>
<style scoped>
.todolist-header{
    height: 60px;
    background-color: rgba(47,47,47,0.98);
}
.todolist-header-container{
    height: 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.todo-serach{
    width: 60%;
    height: 24px;
    margin-top: 12px;
    text-indent: 10px;
    border-radius: 5px;
    box-shadow: 0 1px 0 rgb(255 255 255 / 24%), 0 1px 6px rgb(0 0 0 / 45%) inset;
    border: none;
    outline: none;
}
.todo-title{
    color: #DDD;
}
</style>