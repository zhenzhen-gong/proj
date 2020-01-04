<template>
  <div name="show">
    <ul class="goodlist">
        <li v-for="good in list">
            <img v-bind:src="good.img">
            <p>{{good.goodname}}</p>
        </li>
    </ul>
  </div>
</template>
<style>
  .goodlist li{
      width: 200px;
      height: 200px;
      float: left;
      list-style: none;
      font-size: 9px;
      color:red;
      margin-top: 15px;
  }
  .goodlist img{
      width: 180px;
      height: 180px;
  }
</style>
<script>
   export default{
       name:"show",
       data(){
           var obj=this;
           var url="";
            if(obj.goodId==1){
                   url="json/bjb.json";
               }else if(obj.goodId==2){
                   url="json/shouji.json";
               }else{
                    url="json/bjb.json";
               }
           this.$http.get(url).then(function(res){
               obj.list=res.data;
           })
           return{
               list:[]
           }
       },
       props:{
           goodId:Number
       },
       watch:{
           goodId(){
               var obj=this;
               var url="";
               if(obj.goodId==1){
                   url="json/bjb.json";
               }else if(obj.goodId==2){
                   url="json/shouji.json";
               }else{
                    url="json/bjb.json";
               }
               this.$http.get(url).then(function(res){
                 obj.list=res.data;
               })
               return{
                 list:[]
               }
           }
       }
   }
</script>