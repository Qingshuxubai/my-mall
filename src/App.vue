<template>
  <div id="app">
    <div id="nav">
     <main-tabbar class="maintabbar"></main-tabbar>
    </div>
    <router-view/>
  </div>
</template>
<script>
  import MainTabbar from 'components/content/MainTabbar'
  export default {
    name : 'App' ,
    components :{
      MainTabbar
    }
  }
</script>

<style>
@import url('./assets/css/base.css');
@import url('./assets/css/normalize.css');
.maintabbar{
  position: fixed;
  z-index: 50;
}
</style>
