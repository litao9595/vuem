<template>
  <div class="hello">
    <h5>{{msg}}</h5>
    <h5>{{count()}}</h5>
    <van-button type="primary" @click="increment">主要按钮</van-button>
    <van-button type="primary" @click="bian">主要按钮</van-button>
    <ceshi :chuanzhi="mydata"></ceshi>
  </div>
</template>

<script>
  import {config} from './js/httpConfig'
  import{mapGetters,mapActions} from 'vuex'
  import ceshi from '@/components/ceshi'
export default {
    components:{ceshi},
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      mydata:1
    }
  },
  //创建阶段的生命周期
  beforeCreate:function(){
      console.log("实例化前");
  },
  created:function(){
      console.log("编译完成");
  },
  beforeMount:function(){
      this.su=2;
      console.log("挂载前")
  },
  mounted:function(){
      let _dx=document.getElementById("cc");
      console.log("挂载后")
  },
  //运行阶段生命周期
  beforeUpdate:function(){
      console.log("更新前")
  },
  updated:function(){
      console.log("更新后")
  },
  //销毁阶段生命周期
  beforeDestroy:function(){
      console.log("销毁前")
  },
  destroyed:function(){
      console.log("销毁后")
  },
  methods:{
    ...mapActions(['increment','reduce','resumeList','dataAppId']),
    ...mapGetters(['count']),
    clickBtn(){
      // this.$store.commit('resumeList',10);
      // this.$store.commit('increment');
    },
    bian(){
      this.mydata++
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" rel="stylesheet/less" scoped>
@import "css/style.less";
</style>
