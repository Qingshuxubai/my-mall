<template>
   <div id="nav">
     <slot></slot>
   </div> 
</template>

<script>
 
 export default {
  name : 'Tabbar' ,
 }
</script>
<style scoped>
 #nav{
    display: flex;
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: #f6f6f6;
    box-shadow: 0 , 3px , 2px , rgba(100, 100, 100, 0.2);
    font-size: 14px; 
  }
</style>