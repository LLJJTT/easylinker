<template>
  <div id="app" :style="minHeight+'px'">
    <Header></Header>
    <transition name="slide-fade">
      <router-view/>
    </transition>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from './components/header'
import Footer from './components/footer'
export default {
  name: 'App',
  components:{
    Header,Footer
  },
  data(){
    return{
      minHeight:0
    }
  },
  mounted(){
    this.minHeight = document.documentElement.clientHeight - 120
    let that  = this
    window.onresize = function(){
      that.minHeight = document.documentElement.clientHeight -120
    }
  }
}
</script>

<style>
@import './css/common.css';
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* height: 100%; */
}
.slide-fade{
  position: absolute;left:0;right: 0;
}
.slide-fade-enter-active {
  transition: all 1.8s ease;
}
.slide-fade-leave-active {

  transition: all .3s cubic-bezier(2.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
{
  left:0;right: 0;
  transform: translateX(200px);
  opacity: 0;
}
</style>
