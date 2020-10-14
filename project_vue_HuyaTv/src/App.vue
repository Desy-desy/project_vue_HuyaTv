<template>
  <div class="app" >
    <Header/>
    <HeaderNav></HeaderNav>
    <Up v-show="isShow" :fData="isShow"></Up>
    <router-view/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import HeaderNav from '@/components/HeaderNav.vue'
import Up from '@/components/Up.vue'

export default {
  data(){
    return{
      isShow:true
    }
  },
  components: {
    Header,
    HeaderNav,
    Up
  },
  mounted(){
    let cc= document.getElementsByClassName("app")[0];
    cc.addEventListener('scroll',function(e){
      let a1 = e.target.scrollTop;
      if(a1<800){
        console.log(this.isShow);
        this.isShow=false;
        // this.$forceUpdate();
      }else{
        console.log(this.isShow);
        this.isShow=true;
        // this.$forceUpdate();
      }
      // this.$forceUpdate();
    },false)
  }
}
</script>

<style  scoped>
.app{
  height :100vh;
  overflow-y: auto;
}
</style>
