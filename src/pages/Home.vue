<template>
  <div class="page-main home">
      <img src="./../static/images/index.jpg" @click="go_act" class="index" alt="世界上最浪漫的事，就是和你一起慢慢变老~">
  </div>
</template>

<script type="text/ecmascript-6">

  export default{
    name:'home',

    components:{
    },
    data() {
      return {
        inter:null
      }
    },
    mounted:function(){
      var vm = this;
      if(window.is_change) return;
      vm.inter = setTimeout(function(){
        vm.go_act()
      },3000)
    },
    methods:{
      go_act(){
        this.$router.push({name:'Act'})
        clearInterval(this.inter)
      },
    }
  }
</script>

<style scoped rel="stylesheet/less" lang="less">
  .home {

    .turn{
      color: blue;
      margin: 40px auto;
    }

    .index{
      display: block;
    }
  }
</style>