<template>
    <div>
        <ToDoHeader @addtodo="addtodo"></ToDoHeader>
        <UnderWay :todolists="todolists" @click="finish"></UnderWay>
        <Completed :todolists="finishlists" @click="leavetodo"></Completed>
    </div>
</template>
<script>
//EventBus
import ToDoHeader from './Header';
import UnderWay from './Underway';
import Completed from './Completed';
export default{
    components:{
        ToDoHeader,
        UnderWay,
        Completed,
    },
    data(){
        return{
            todolists:[],
            finishlists:[],
        }
    },
    methods:{
        addtodo(obj){
            this.todolists.push(obj); 
        },
        finish(item){
            this.finishlists.push(item)
        },
        leavetodo(item){
            this.todolists.push(item);
        }
    }

}</script>
<style>
.todolist-container{
    width: 600px;
    margin: 0 auto;
}

</style>