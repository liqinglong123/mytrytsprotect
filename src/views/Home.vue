<template>
  <div>
    <template>
      <el-carousel :interval="4000" type="card" height="200px">
        <el-carousel-item v-for="item in 6" :key="item">
          <h3 class="medium">{{ item }}</h3>
        </el-carousel-item>
      </el-carousel>
    </template>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  /*components: {
    HelloWorld
  }*/
  data(){
    return{

    }
  },
  mounted(){
    this.init()
  },
  methods:{
    init(){
      this.$axios.get('http://www.zq100.com/api/basic/search/hotword').then(res => {
        console.log(res, '我的數據')
      })
    }
  }
}
</script>
<style lang="scss" scoped>
  .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 200px;
    margin: 0;
  }

  .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }

  .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  }
</style>
