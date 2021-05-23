<template>
  <div><tabbar>
      <tabbaritem path="/home" activeColor="red">
        <img  slot="item-img" src="~assets/img/tabbar/tabbar_首页_默认.svg" >
      <img  slot="item-img-select" src="~assets/img/tabbar/tabbar-首页-选中.svg">
        <div slot="item-text">首页</div>
      </tabbaritem>
       <tabbaritem path="/category" activeColor="red">
        <img  slot="item-img" src="~assets/img/tabbar/tabbar-分类.svg" >
        <img  slot="item-img-select" src="~assets/img/tabbar/tabbar_分类icon-已选中.svg">
        <div slot="item-text">分类</div>
      </tabbaritem>
       <tabbaritem path="/cart" activeColor="red">
        <img  slot="item-img" src="~assets/img/tabbar/tabbar_购物车未选中.svg" >
        <img  slot="item-img-select" src="~assets/img/tabbar/tabbar-购物车-选中.svg">
        <div slot="item-text">购物车</div>
      </tabbaritem>
       <tabbaritem path="/profile" activeColor="red">
        <img  slot="item-img" src="~assets/img/tabbar/tabbar-我的-默认.svg" >
        <img  slot="item-img-select" src="~assets/img/tabbar/tabbar-我的-选中.svg">
        <div slot="item-text">我的</div>
      </tabbaritem>
   </tabbar></div>
</template>

<script>
    import Tabbar from 'components/tabbar/Tabbar'
    import Tabbaritem from 'components/tabbar/tabbar-item'
export default {
    name : 'MainTabbar' ,
    components :{
    Tabbar ,
    Tabbaritem
    }
}
 
</script>
<style scoped>
</style>