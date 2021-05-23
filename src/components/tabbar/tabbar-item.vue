<template>
  <div @click="Citem" class="tabbar-item">
     <template>
      <slot v-if="select" name="item-img"></slot>
      <slot v-else name="item-img-select"></slot>
      <div :style=activeStyle><slot  name="item-text"> </slot></div>
     </template>
  </div>
</template>

<script>
export default {
  props:{
    path : String ,
    activeColor :{
         type : String ,
         default : 'red'
       }
  } ,
   data() {
     return {
       //select : false

     }
   },
   computed: {
     select(){
       return this.$route.path !== this.path
     },
     activeStyle(){
       return this.select ? {} :{color:this.activeColor}
     }
   },
   methods: {
     Citem(){
       this.$router.push(this.path)
     }
   }
}

</script>
<style scoped>
.tabbar-item{
    flex: 1;
    text-align: center;
    height: 49px;
  }
  .tabbar-item img{
    width: 24px;
    height: 24px;
    margin-top: 5px;
    vertical-align: middle;
  }
</style>