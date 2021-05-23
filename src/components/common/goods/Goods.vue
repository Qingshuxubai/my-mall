<template>
  <div class="goods">
      <goods-item v-for="(item, id) in goodslist" :goods-item="item" :key="id"></goods-item>
  </div>
</template>

<script>
import GoodsItem from './GoodsItem.vue'
export default {
    name : 'Goods' ,
    components: { 
      GoodsItem 
    } ,
    props : {
        goodslist : {
            type : Array ,
            data() {
                return []
            }
        }
    }
}

</script>
<style scoped>
.goods {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;

    padding: 2px;
  }

</style>