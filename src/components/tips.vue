<template>
  <div class="tips">
    <a href="">{{msg}}</a>
  </div>
</template>

<script>
  export default{
    name:'tips',
    data:function () {
      return {
        msg:'假设这是一个弹窗' 
      }
    }
  }
</script>

<style scoped rel="stylesheet/less" lang="less">
  .tips{
    width: 20%;
  }
</style>