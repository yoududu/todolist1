<template>
    <div class="todo-items">
        <input type="checkbox" class="underway-ck" @change="finish(index)" :checked="state">
        <p>{{content}}</p>
        <span class="todo-del" @click="del(index)">-</span>
    </div>
</template>
<script>
export default{
    props:{
        content:String,
        index:Number,
        state:{
            default(){
                return false;
            }
        }
    },
    methods:{
        del(index){
            this.$emit("deletee",index)
        },
        finish(index){
            this.$emit("click",index);
        }
    }
}
</script>
<style>
.todo-items{
    height: 32px;
    line-height: 32px;
    background: #fff;
    margin-bottom: 10px;
    border-radius: 3px;
    border-left: 5px solid #999;
    box-shadow: 0 1px 2px rgb(0 0 0 / 7%);
    display: flex;
    flex-direction: row;
    align-items: center;
    user-select: none; /*不可选中*/
    opacity: 0.5;
}
.underway-ck{
    width: 22px;
    height: 22px;
    cursor: pointer;
    margin-left: 12px;
}
.todo-items p{
    width: 505px;
    margin: 0px;
    padding: 0px 10px;
}
.todo-del{
    display: inline-block;
    width: 14px;
    height: 12px;
    border-radius: 14px;
    border: 6px double #FFF;
    background: #CCC;
    line-height: 14px;
    text-align: center;
    color: #FFF;
    font-weight: bold;
    font-size: 14px;
    cursor: pointer;
    margin-left: 5px;
}
</style>