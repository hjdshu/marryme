<template>
  <div class="app">
    <transition name="slide-fade" model="out-in">
      <router-view :isMusic="music"></router-view>
    </transition>
    <Tips v-show="false"></Tips>
    <audio src="./static/bgm.mp3" id="music" autoplay="true" loop="true"></audio>
    <div class="music" @click="play">
      <img src="./static/images/music.png" v-show="music" alt="">
      <img src="./static/images/nomusic.png"  v-show="!music" alt="">
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import Tips from './components/tips.vue'

  export default{
    name:'app',
    components:{
      Tips
    },
    data:function () {
      return {
        music:true,
      }
    },
    mounted:function(){
      window.is_change = false;

    },
    methods:{
      play:function(){
        var music =  document.getElementById('music')
        if(this.music){
          music.pause();
          this.music = false;
        }else{
          music.play()
          this.music = true;
        }
      }
    }
  }
</script>

<style rel="stylesheet/less" lang="less">
  @import "./static/css/base.less";
</style>


<style scoped rel="stylesheet/less" lang="less">
.app{

  .music{
    position: fixed;
    top:30px;
    right:30px;
  }
  font-size: 40px;

  /* 可以设置不同的进入和离开动画 */
  /* 设置持续时间和动画函数 */
  .slide-fade-enter-active {
    transition: all 0.5s ease 0.2s;
    transform: translateX(0);
    opacity: 1;
  }
  .slide-fade-leave-active {
    transition: all 0.5s ease;
    transform: translateY(70px);
    opacity: 0;
  }

  .slide-fade-enter{
    transform: translateX(-70px);
    opacity: 0;
  }
  .slide-fade-leave{
    transform: translateY(0);
  }

}
</style>