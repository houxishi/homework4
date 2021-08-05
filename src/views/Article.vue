<template>
  <div class="about" >
    <div v-for="item in article" :key="item.id">
    <table>
    <tr>题目：{{item.title}}</tr>
    <tr>摘要：{{item.summary}}</tr>
    <tr>内容：{{item.content}}</tr>
    <tr>
      <span class="right">类型：{{item.kind}}</span>
      <span class="right">来源：{{item.tags}}</span>
      <span class="right">评论状态：{{item.commentState}}</span>
      <span class="right">状态：{{item.state}}</span>
      <span @mousemove="show(item.id,1)" @mouseleave="show(item.id,2)">
        {{item.time}}
        <div class="time" :style="{display:dict[item.id].name}">具体时间：{{item.spec}}</div>
      </span>
    </tr>
    </table>
    </div>
  </div>
</template>

<script>
import api from '@/api/index'

export default {
 data(){
   return{
     article:[],
     dict:[{name:'none'},
     {name:'none'}]
   }
 },
 methods:{
   async onSearch(){
     this.list=await api.test();
     this.article=this.list.data.data.tablelist
   },
   show:function(i,val){
     if(val==1)
      {this.dict[i].name='block'}
      else{
        this.dict[i].name='none'
      }
   }
 },
 created(){
   this.onSearch()
 }
}
</script>

<style scoped>
table{
  margin-top: 5px;
  border-top: 2px solid rgb(187, 183, 183);
  border-bottom: 2px solid rgb(187, 183, 183);
}
tr{ 
  text-align:left;
}
.right{
  padding-right: 3px;
  margin-right: 10px;
  border-right: 2px solid rgb(187, 183, 183);
}

</style>