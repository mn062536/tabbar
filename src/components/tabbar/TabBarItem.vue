<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive"><slot name="item-icon"></slot></div>
    <div v-else><slot name="item-icon-active"></slot></div>
    <div :style="isActive ? {color:this.activeColor}:{}"><slot name="item-text"></slot></div>
  </div>
</template>

<script>
  export default {
    name: "TabBarItem",
    props:{
      link:String,
      activeColor:{
        type:String,
        default:'red'
      }
    },
    data(){
      return{
        // isActive:true,
        path:'/'
      }
    },
    computed:{
      isActive(){
        return this.$route.path.indexOf(this.link) !== -1;
      }
    },
    methods:{
      itemClick(){
        this.$router.replace(this.link).catch(err=>{})
      }
    }
  }
</script>

<style scoped>
  .tab-bar-item{
    flex: 1;
    text-align: center;
    font-size: 14px;
  }
  .tab-bar-item img{
    width: 24px;
    margin-top: 3px;
    vertical-align: middle;
  }
  /* .active{
    color: red;
  } */
</style>
