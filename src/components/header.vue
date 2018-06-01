<template>
  <div id="header">
    <div class="container">
    	<!-- logo -->
    	<div class="logo">
    		<img src="static/img/logo.png" alt="云易联" title="云易联">
    		<span>云易联CloudEasyLinker</span>
    	</div>

			<!-- 导航 -->
    	<div class="tab">
	        <router-link :to="item.path" v-for="item in tabs" :key="item.key" @click.native="handlClick(item.key)" :class="item.key == tab ? 'active' : ''" >
	            {{ item.name }}
	        </router-link> 
    	</div>

    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
    	tabs: [{
        name: '产品服务',
        path: 'home',
        key: 1,
      },{
        name: '开发平台',
        path: 'development_platform',
        key: 2,
      },{
        name: '客户案例',
        path: 'customer_case',
        key: 3,
      },{
        name: '开发者社区',
        path: 'developer_community',
        key: 4,
      },{
        name: '文档',
        path: 'file',
        key: 5,
      },{
        name: '关于我们',
        path: 'about_us',
        key: 6,
      }],
      tab: '1'
    }
  },
  methods: {
    handlClick (e) {
      this.tab = e
      // console.log(this.tab)
    }
  }
}
</script>

<style scoped>
	#header{
		height: 60px;
	}
	.container{
		width: 100%;
		height: 60px;
		background: #454a61;
		text-align: right; 
	}
	.logo{
		display: inline-block;
		margin-top: 10px;
		position: absolute;
		left: 8%;
	}
	.logo img{
		width: 40px;
		height: 40px;
		vertical-align: middle;
	}
	.logo span{
		margin-left: 40px;
		color: #fff;
		font-weight: bolder;
		letter-spacing: 1px;
	}
	.tab{
		height: 60px;
		line-height: 60px;
		vertical-align: middle;
		display: inline-block;
		margin-right: 14%;
	}
  .tab  a{
    font-size: 14px;
    font-weight: bolder;
    /* color: #fff; */
    cursor: pointer;
    margin-left: 15px;
  }
  .tab a:hover{
  	transition: .4s;
		color: #ded60f;
		padding-bottom: 4px;
		border-bottom: 2px solid #ded60f;
  }
  .tab .active{
  	transition: .8s;
  	color: #ded60f;
  }

</style>
