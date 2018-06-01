<template>
  <div id="footer">
    <div class="container">
        <ul>
          <li><img class="logo" src="static/img/logo.png" alt="">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;版权所有&nbsp;&copy;&nbsp;云易联&nbsp;<i>CloudEasyLinker</i></li>
        </ul>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
    	
    }
  },
  methods: {
    
  }
}
</script>

<style scoped>
	#footer{
		height:60px;
    background: #222222;
    line-height: 60px;
    color: #767676;
    margin-top: 60px;
	}
  .container{
    font-weight: bolder;
  }
  .container ul li i:hover{
    transition: .5s;
    color: red;
  }
  .logo{
    display: inline-block;
    width: 40px;
    height: 40px;
    vertical-align: middle;
  }
</style>
