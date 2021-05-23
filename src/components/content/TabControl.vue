<template>
  <div class="tab-ctrl">
      <div v-for="(item , index) in titles" :key="index" 
      class="item" :class="{active : index === currentindex}"  @click="itemclick(index)">
          <span class="title">{{item}}</span>
      </div>
  </div>
</template>

<script>
export default {
    name : 'TabControl' ,
    props : {
        titles : {
            type : Array ,
            data() {
                return []
            }
        } 
    } ,
    data() {
        return {
            currentindex : 0
        }
    },
    methods :{
        itemclick(index){
            this.currentindex = index 
            this.$emit('ChangeType' ,index)
        }
    }
}
</script>
<style scoped>
.tab-ctrl{
    display: flex;
    width: 100%;
    text-align: center;
    font-size: 14px;
    padding: 5px;
    background-color: #fff;
    position: sticky;
    top: 44px;
    z-index: 50;
}
.item{
    flex: 1;
    height: 30px;
    line-height: 30px;
}
.title{
    width: 15px;
    padding: 5px;
}
.active span{
    color: var( --color-high-text);
    border-bottom: 3px solid var( --color-high-text);
}
</style>