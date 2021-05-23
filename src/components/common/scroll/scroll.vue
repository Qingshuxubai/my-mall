<template>
  <div ref="box">
      <slot></slot>
  </div>
</template>

<script>
export default {
    name : 'Scroll' ,
   mounted () {
       
    window.addEventListener('scroll', this.handleScroll)
   },
   destroyed () {
   window.removeEventListener('scroll', this.handleScroll)
   }, 
   methods : {
       handleScroll () {
       //变量scrollTop是滚动条滚动时，距离顶部的距离
       var scrollTop = document.documentElement.scrollTop||document.body.scrollTop;
       //变量windowHeight是可视区的高度
       var windowHeight = document.documentElement.clientHeight || document.body.clientHeight;
       //变量scrollHeight是滚动条的总高度
       var scrollHeight = document.documentElement.scrollHeight||document.body.scrollHeight;
       //滚动条到底部的条件
       if(scrollTop+windowHeight==scrollHeight ){
           this.$emit('loadmore')
       }
   }
   }
}
</script>
<style scoped>
</style>