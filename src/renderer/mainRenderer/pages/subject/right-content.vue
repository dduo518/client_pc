<template>
    <div class="right-container">
		<router-view name='childSubject'></router-view>
		
	</div>
</template>

<script>
    export default {
  name: 'rightContainer'
    }
</script>

<style scoped>
/*********************
* 内容区布局
*********************/
.content .right-container{
    width: 100%;
    height: 100%;
    padding: 0px 0px 0px 200px;
}
.content .right-container>div{
	padding:20px;
	
}

.content .right-container .container-nav{
	float: left;
	width: 100%;
}
.content .container-nav li{
	height: 28px;
	float: left;
	text-align: center;
	padding-bottom: 6px;
	cursor: pointer;
	border-bottom: 4px solid transparent;
}
.content .container-nav li:hover{
	height: 28px;
	border-bottom: 4px solid #a8c4dd;
}
.right-box{
	width: 100%;
	height: 100%;
}
</style>