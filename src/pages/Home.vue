<template>
  <div class="page-main home" @click="go_act">
     <img src="./static/images/index.jpg" alt="" class="index">
  </div>
</template>

<script type="text/ecmascript-6">

  export default{
    name:'home',
    props:['isMusic'],
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
      },5000)
    },
    methods:{
      go_act(){
        this.$router.push({name:'Act'})
        var music =  document.getElementById('music')

        if(this.isMusic){
         music.play()
        }
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