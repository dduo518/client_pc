<template>
        <!-- 左边列表 -->
	<div class="nav">
		<ul>
				<li v-for="(relation,index) in relations" class="oli" v-bind:class="{active:nowId==relation.id}" :key="index" @click='changeView($event,relation)'>			
						<span class="navIcon"  v-bind:class="relation.class"></span><a >{{relation.text}}</a>
				</li>
		</ul>
	</div>	
</template>
<script>
export default {
  data () {
    return {
      nowId: 'index',
      relations: [
        {text: '首页', id: 'index', class: 'order'},
        {text: '课程', id: 'subject', class: 'statistical'},
        {text: '学生', id: 'student', class: 'person'},
        {text: '教师', id: 'teacher', class: 'inventory'},
        // {text: '收费', id: 'charge', class: 'charge'},
        // {text: '微信', id: 'wechat', class: 'wechat'},
        {text: '设置', id: 'setting', class: 'setting'}
      ]
    }
  },
  methods: {
    changeView (ev, relation) {
			this.nowId = relation.id;
      this.$router.replace('/'+relation.id)
    }
  }
}
</script>

<style scoped>
 .nav{
	height: 100%;
	width: 54px;
	z-index: 3;
	background-image: -moz-linear-gradient(top, #15558a, #9bd7f6); /*火狐*/
	background: -webkit-linear-gradient(#15558a 0%, #9bd7f6 100%);
	background: -o-linear-gradient(#15558a 0%, #9bd7f6 100%);
	background: linear-gradient(#15558a 0%, #9bd7f6 100%);/*Opera*/
	background-image: -webkit-gradient(linear, left top, left bottom, color-stop(0, #15558a), color-stop(1,#9bd7f6)); /*Chrome*/
	filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#15558a', endColorstr='#9bd7f6', GradientType='0'); /*IE*/
}
 .nav li{
	width: 50px;
	height: 56px;
	cursor: pointer;
	text-align: center;
	padding: 10px 0;			
}
 .nav li:hover{
	background: #144C89;
	border-right: 4px solid #9FD5F7;
}

 .nav a{color: #FFF;font-size: 12px;}
 .nav .oli{
	border-right: 4px solid transparent;
}
 .nav .active{
	background: #144C89;
	border-right: 4px solid #9FD5F7;
}
 .nav .navIcon{
	width: 24px;
	height: 25px;
	display:block;
	margin: 0 auto;
}
 .nav .order{
	background: url('./../../assets/img/icon/1.png') no-repeat!important;
}
 .nav .person{
	background: url('./../../assets/img/icon/2.png') no-repeat!important;
}
 .nav .charge{
	background: url('./../../assets/img/icon/3.png') no-repeat!important;
}
 .nav .statistical{
	background: url('./../../assets/img/icon/4.png') no-repeat!important;
}
 .nav .inventory{
	background: url('./../../assets/img/icon/5.png') no-repeat!important;
}

 .nav .setting{
	background: url('./../../assets/img/icon/6.png') no-repeat!important;
}
.nav .wechat{
	background: url('./../../assets/img/icon/wx.png') no-repeat!important;
}
 .listbox{
	float: left;
	height: 743px;
}
</style>