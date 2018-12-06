<template lang="html">
  <div>
    <div class="carousel">
      <el-carousel :interval="4000" type="card" height="200px">
        <el-carousel-item v-for="item in 6" :key="item">
          <img :src="imgUrl">
          <!-- <h3>{{ item }}</h3> -->
        </el-carousel-item>
      </el-carousel>
    </div>

    <div class="section">
      <div class="section1">
        <el-card class="box-card">
          <div class="clearfix" slot="header">
            <span>版块1</span>
            <el-button style="float: right; padding: 3px 0" type="text">更多</el-button>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容 " + o }}
          </div>
        </el-card>
      </div>

      <div class="section2">
        <el-card class="box-card">
          <div class="clearfix" slot="header">
            <span>版块2</span>
            <el-button style="float: right; padding: 3px 0" type="text">更多</el-button>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容 " + o }}
          </div>
        </el-card>
      </div>

      <div class="section3">
        <el-card class="box-card">
          <div class="clearfix" slot="header">
            <span>版块3</span>
            <el-button style="float: right; padding: 3px 0" type="text">更多</el-button>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容 " + o }}
          </div>
        </el-card>
      </div>

      <div class="section4">
        <el-card class="box-card">
          <div class="clearfix" slot="header">
            <span>版块4</span>
            <el-button style="float: right; padding: 3px 0" type="text">更多</el-button>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容 " + o }}
          </div>
        </el-card>
      </div>
    </div>

  </div>
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

.text {
  font-size: 14px;
}

.item {
  margin-bottom: 18px;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}

.clearfix:after {
  clear: both
}

.box-card {
  width: 480px;
}

.section1 {
  padding-right: 5.5em;
  float: right;
}

.section3 {
  margin-top: 3.5em;
  float: right;
  padding-right: 5.5em;
}

.section2 {
  padding-left: 5.5em;
}

.section4 {
  margin-top: 3.5em;
  padding-left: 5.5em;
}

</style>
