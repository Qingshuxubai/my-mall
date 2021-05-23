<template>
  <div class="recommend">
      <div class="re-item" v-for="(item , id) in recommend" :key="id">
          <a :href="item.link">
              <img :src="item.image" alt="">
          </a>
          <div>{{item.title}}</div>
      </div>
  </div>
</template>

<script>
export default {
    name : 'RecommendView' ,
    props : {
        recommend :{
            type : Array ,
            default(){
                return []
            }
        }
    }
}

</script>
<style scoped>
.recommend{
    width: 100%;
    display: flex;
    font-size: 12px;
    padding: 10px 0 20px;
    text-align: center;
    border-bottom: 10px solid #eee;
}
.re-item{
    flex: 1;
}
.recommend img{
    width: 70px;
    height: 70px;
    margin-bottom: 5px;
}
</style>