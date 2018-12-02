<template lang="html">
  <el-carousel :interval="4000" type="card" height="200px">
    <el-carousel-item v-for="item in 6" :key="item" >
      <img :src="imgUrl">
      <!-- <h3>{{ item }}</h3> -->
    </el-carousel-item>
  </el-carousel>
</template>

<script>
export default {
  name: 'homepage',
  data(){
    return{
      imgUrl:''
    }
  },
  created:function(){
    this.changeimgUrl()
  },
  methods:{
    changeimgUrl(){
      // console.log(this)
      // this.imgUrl='http://turbulent.cn:5000/images/a.jpg'
      // return  this.imgUrl
      this.$axios.get('http://turbulent.cn:5000/test')
        .then( (response) =>{
            console.log(response);
            })
        .catch((error)=> {
          console.log(error);
            })
    }
  }
}

</script>

<style lang="css">
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
