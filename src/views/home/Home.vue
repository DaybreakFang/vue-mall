<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <h2>首页</h2>

  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'
import {getHomeData} from 'network/home'
export default {
  components:{
    NavBar
  },
  data(){
    return {
      banner:[],
    recommend:[]
    }
  },
  created(){
    getHomeData().then(res=>{
      console.log(res);
      this.banner =res.data.banner.list;
      this.recommend = res.data.recommend.list;
    })
  }
}

</script>
<style  scoped>
.home-nav{
  background-color: var(--color-tint);
  color: #fff;
}
</style>