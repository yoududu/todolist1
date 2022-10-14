<template>
    <div class="todo-underway todolist-container">
        <div class="todo-underway-header">
            <h2>已经完成</h2>
            <span class="todo-count">{{todolists.length}}</span>
        </div>
        <div class="todo-underway-item">
            <transition-group enter-active-class="animate__animated animate__fadeInLeft" leave-active-class="animate__animated animate__fadeOutRight">
            <Items v-for="(item,index) of todolists" 
            :key="item.id" 
            :content="item.content" 
            :index="index"
            @deletee="deletee"
            :state="true"
            @click="leavetodo"></Items>
        </transition-group>
        </div>
    </div>
</template>
<script>
import Items from './Items.vue';
export default{
    props:["todolists"],
    components:{
    Items
},
    methods:{
        deletee(index){
            this.todolists.splice(index,1)
        },
        leavetodo(index){
            let item = this.todolists.splice(index,1)[0];
            this.$emit("click",item)
        }
    },

}</script>
<style scoped>
.todo-underway-header{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.todo-count{
    display: inline-block;
    padding: 0 5px;
    height: 20px;
    border-radius: 20px;
    background: #E6E6FA;
    line-height: 22px;
    text-align: center;
    color: #666;
    font-size: 14px;
}
</style>