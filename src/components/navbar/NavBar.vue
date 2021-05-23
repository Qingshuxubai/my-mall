<template>
  <div class="nav-bar">
      <div class="nav-left"><slot name="nav-left"></slot></div>
      <div class="nav-center"><slot  name="nav-center"></slot></div>
      <div class="nav-right"><slot name="nav-right"></slot></div>
  </div>
</template>

<script>
export default {
    name : 'NavBar' 
}

</script>
<style scoped>
.nav-bar{
    display: flex;
    height: 44px;
    line-height: 44px;
    color: whitesmoke;
    text-align: center;
    box-shadow: 0 1px 2px rgba(100, 100, 100, 0.2);
}
.nav-left{
    width: 69px;
}
.nav-right{
    width: 69px;
}
.nav-center{
    flex: 1;
}
</style>