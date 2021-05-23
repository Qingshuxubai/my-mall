<template>
  <div id="home" ref="scr">
    <scroll @loadmore="loadmore" > 
    <nav-bar class="home-nav">
      <div slot="nav-left"></div>
      <div slot="nav-center">购物街</div>
      <div slot="nav-right"></div>
    </nav-bar>
    <home-swiper :banners = "banners"></home-swiper>
    <recommend-view :recommend = "recommend"></recommend-view>
    <feature></feature>
    <tab-control :titles="['流行' , '新款' , '精选']" @ChangeType="ChangeType"></tab-control>
    <goods :goodslist="goods[currenttype].list"></goods>
    </scroll>
  </div>
</template>

<script>
/* 子组件 */
import HomeSwiper from './childhome/HomeSwiper'
import RecommendView from './childhome/RecommendView'
import Feature from './childhome/feature'

/* 公共组件*/ 
import NavBar from 'components/navbar/NavBar'
import TabControl from 'components/content/TabControl'
import Goods from 'components/common/goods/Goods'
import Scroll from 'components/common/scroll/scroll'


/* 封装方法*/ 
import {getHomeMultidata , getHomeGoods} from 'network/home'
export default {
 name : 'Home' ,
 data() {
   return {
     banners : [] ,
     recommend : [] ,
     goods : {
       'pop' : {page : 0 , list : []} ,
       'new' : {page : 0 , list : []} ,
       'sell' : {page : 0 , list : []} 
     } ,
     currenttype : 'pop' 
   }
 }, 
 components : {
   NavBar ,
   HomeSwiper ,
   RecommendView ,
   Feature ,
   TabControl ,
   Goods ,
   Scroll
 } ,
 created(){
   this.getHomeMultidata()

   this.getHomeGoods('pop')
   this.getHomeGoods('new')
   this.getHomeGoods('sell')
  } ,
  methods :{
    getHomeMultidata(){
      getHomeMultidata().then(res =>{
        console.log(res);
        this.banners = res.data.banner.list;
        this.recommend = res.data.recommend.list;
      })
    } ,
    getHomeGoods(type){
      const page = this.goods[type].page + 1
      getHomeGoods(type , page).then(res => {
        console.log(res)
        this.goods[type].list.push(...res.data.list)
        this.goods[type].page += 1
      })
    } ,
    ChangeType(index){
      switch (index){
        case 0 :
          this.currenttype = 'pop' 
          break
        case 1 :
          this.currenttype = 'new'
          break
        case 2 :
          this.currenttype = 'sell'
          break
      }
    } ,
    loadmore(){
      console.log(this.currenttype);
      this.getHomeGoods(this.currenttype)
    }
  }
 }

</script>
<style scoped>
.home-nav{
    background-color: var(--color-tint);
    position: sticky;
    top: 0;
    z-index: 5;
}
</style>