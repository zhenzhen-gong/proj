<template>
  <div>
      <div v-if="kk==1">
          <GoodList :goodId="1"></GoodList>
      </div>
      <div v-else-if="kk==2">
          <GoodList :goodId="2"></GoodList>
      </div>
      <div v-else-if="kk==3">
          333333333333333333
      </div>
      <div v-else-if="kk==4">
          444444444444444444
      </div>
      <div v-else>
          <GoodList :goodId="0"></GoodList>
      </div>
  </div>
</template>
<script>
  import Msg from "./msg.js"
  import GoodList from "./goodslist.vue"
    export default{
      data(){
          return{
              kk:0
          }
      },
      mounted:function(){
         var _this=this
         Msg.$on("val",function(m){
             _this.kk=m;
         })
      },
      components:{
        GoodList   
      }
  }
</script>