<template>
  <div id="home">
    <div class="move">
      <el-carousel :interval="3000" arrow="never" height="500px">
        <el-carousel-item v-for="item in moverImg" :key="item.key">
          <img class="banner" :src="item.src">
        </el-carousel-item>
      </el-carousel>
    </div>
    <div class="service">
      <h1><span>CloudEasyLinker</span>服务模块</h1>
    </div>
    <!-- 服务下的模块 -->
    <div class="service_block">
      <el-row :gutter="20">
        <el-col :span="6">
          <div class="block standard">支持模块1</div>
        </el-col>
        <el-col :span="6">
          <div class="block standard">支持模块2</div>
        </el-col>
        <el-col :span="6">
          <div class="block standard">支持模块3</div>
        </el-col>
        <el-col :span="6">
          <div class="block standard">支持模块4</div>
        </el-col>
      </el-row>
    </div>

    <!-- 动态 -->
    <div class="service">
      <h1>CloudEasyLinker最新动态</h1>
    </div>
<!-- 动态下栏目 -->

    <div class="service_block">
      <div class="wrapper">
        <el-row :gutter="40">
          <el-col :span="6">
            <div class="block">这里是图片</div>
          </el-col>
          <el-col :span="18">
            <div class="block">这里还有很多新闻内容</div>
          </el-col>
        </el-row>
      </div>
    </div>

    <!-- 联系我们 -->
    <div class="contact_us">
      <div style="text-align:left;text-indent:30%;font-size: 16px;color: #8f8987;
      padding-bottom: 10px;background: #f3f3f3;">我们的位置</div>
      <el-row :gutter="40">
          <el-col :span="18">
            <div class="map" id="allmap" ref="allmap">
              
            </div>
          </el-col>
          <el-col :span="6">
            <div class="map1">
              <ul class="contact_ul">
                <li class="word">联系我们</li>
                <li><i>电话:</i>&nbsp;&nbsp;<span>8888-8888</span></li>
                <li><i>QQ:</i>&nbsp;&nbsp;<span>751957846</span></li>
                <li @mouseover="showCode" @mouseout="hiddenCode" id="weixin" style="position: relative;"><i>微信:</i>&nbsp;&nbsp;<span>751957846</span><img :style="code" class="qrcode" src="static/img/weixin.jpeg" alt=""></li>
                <li><i>微博:</i>&nbsp;&nbsp;<span>751957846</span></li>
              </ul>
            </div>
          </el-col>
        </el-row>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      moverImg:[{
          src:'static/img/banner1.png',
          key:1
      },{
        src:'static/img/banner2.png',
        key:2
      },{
        src:'static/img/banner3.png',
        key:3
      }],
      code:'display:none'
    }
  },
  methods:{
    // 加载地图
    loadMap(){
      let map =new BMap.Map(this.$refs.allmap); // 创建Map实例  
      var point = new BMap.Point(118.6517276292, 24.9404072550); //华侨大学
      map.centerAndZoom(point,14);// 初始化地图,设置中心点坐标和地图级别  
      map.addControl(new BMap.MapTypeControl({//添加地图类型控件  
        mapTypes:[  
          BMAP_NORMAL_MAP,  
          BMAP_HYBRID_MAP  
        ]}));  
      map.setCurrentCity('北京');// 设置地图显示的城市 此项是必须设置的  
      map.enableScrollWheelZoom(true); //开启鼠标滚轮缩放  
    },
    // 展示二维码
    showCode(){
      this.code = 'display:block'
    },
    // 隐藏二维码
    hiddenCode(){
      this.code = 'display:none'
    }
  },
  mounted(){
      this.loadMap()
    }
}
</script>

<style scoped>
#home{
  height: 100%;
  /* background: #cae8f8; */
}
  .banner{
    width: 100%;
    height: 100%;
  }
  .service h1{
    font-size: 38px;
    font-weight: bolder;
    margin-top: 40px;
    letter-spacing: 10px;
    color: #4e4849;
    padding-bottom: 10px;
    /* border-bottom: 1px solid #f5f5f5; */
  }
  .service h1 span{
    font-size: 36px;
    letter-spacing: 4px;
  }
  .service_block{
    margin-top: 40px;
    padding: 0 20px;
    border-bottom: 4px solid #f8dbdb;
  }
  .block{
    height: 200px;
    background: #cae8f8;
    line-height: 200px;
    box-shadow: #666 0px 0px 10px;
  }
  .standard:hover{
    cursor: pointer;
    box-shadow: #666 0px 0px 40px;
    transition:.6s;
  }
  .contact_us{
    margin-top: 40px;
    padding: 0 20px;
    border: 1px solid #e3d6d6;
    box-shadow: #666 0px 0px 20px;

  }
  .map{
    width: 100%;
    height: 400px;
    background: #cae8f8;
    line-height: 400px;
    overflow: hidden;
  }
  .map1{
    width: 100%;
    height: 400px;
    line-height: 60px;
    border: 1px solid #e3d6d6;
    box-shadow: #666 0px 0px 40px;
  }

  .contact_ul li i{
    font-size: 14px;
    color: #000;
  }
  .contact_ul li span{
    color: #000;
    font-size: 16px;
  }
  .word{
    line-height: normal;
    font-size: 20px;
    color: #7f5d3a;
    display: inline-block;
    padding-bottom:6px;
    border-bottom: 1px solid #b2b2b2;
  }
  .qrcode{
    display: none;
    width: 240px;
    height: 240px;
    vertical-align: middle;
    background: #000;
    position: absolute;
    margin-top: -45%;
    right:0%;
    transition: 1s;
  }
  #weixin{
    background: #ef7171;
    cursor: pointer;
  }
</style>








