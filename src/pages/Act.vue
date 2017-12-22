<template>
  <div class="act page-main">
    <div class="container">
      <div class="">{{msg}}</div>
      <div>亲爱的{{name}}</div>
      <a class="" v-bind:href="mapLink"  >地图</a>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import jsuri from 'jsuri'
  export default{
    name:'act',
    components:{
    },
    data:function () {
      return {
        msg:'世界上最浪漫的事，就是和你一起慢慢变老~',
        name:'',
        mapLink:'https://m.amap.com/share/index/__q=31.55542399312825,107.14299961924554,%E5%9B%9B%E5%B7%9D%E7%9C%81%E5%B7%B4%E4%B8%AD%E5%B8%82%E5%B9%B3%E6%98%8C%E5%8E%BF%E4%B8%9C%E5%9F%8E%E8%BD%A6%E7%AB%99%E9%99%84%E8%BF%91-%E4%BD%95%E5%AE%B6%E5%9D%A1(&src=app_share&callnative=1&callapp=0&lnglat=107.14299961924554,31.55542399312825&name=%E5%9B%9B%E5%B7%9D%E7%9C%81%E5%B7%B4%E4%B8%AD%E5%B8%82%E5%B9%B3%E6%98%8C%E5%8E%BF%E4%B8%9C%E5%9F%8E%E8%BD%A6%E7%AB%99%E9%99%84%E8%BF%91-%E4%BD%95%E5%AE%B6%E5%9D%A1'
      }
    },
    mounted:function(){
      setTimeout(function(){ window.is_change = true;},30)
      var URL = new jsuri(window.location.href)
      this.name = URL.getQueryParamValue('name')
    }

  }
</script>

<style scoped rel="stylesheet/less" lang="less">
  .act {
    a {
      color: red;
    }
  }
</style>