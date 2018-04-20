<template>
	<header class="header">
		<div class="container">
			<router-link to="/"><img src="http://placehold.it/40x40" /></router-link>
			<nav class="main-nav">
				<div class="nav-phone-show el-icon-menu" @click="showMenu=!showMenu"></div>
				<ul class="nav-phone-hide">
					<li><router-link to="/mainpage/mainpage">首页</router-link></li>
					<li><router-link to="/">评论搜索</router-link></li>
					<li><router-link to="/">意见反馈</router-link></li>
				</ul>
				<span>登录注册</span>
			</nav>
		</div>
		<ul class="phone-menu" :class="{'active':showMenu}">
			<li>首页</li>
			<li>评论搜索</li>
			<li>意见反馈</li>
		</ul>
	</header>
</template>

<script>
	export default {
		name: 'header',
		data() {
			return {
				showMenu:false
			}
		},
		methods: {

		},
		components: {}

	}	
</script>

<style scoped="scoped">
	.header {
		width: 100%;
		height: 60px;
		background-color: rgba(102, 153, 204, 1);
		font-size: 20px;
		color: white;
	}
	
	.container {
		position: relative;
		max-width: 1000px;
		height: 100%;
		margin: 0 auto;
		padding: 0 20px;
		display: flex;
		-webkit-box-align: center;
		-ms-flex-align: center;
		align-items: center;
	}
	
	.container img {
		margin-right: 2rem;
	}
	
	.main-nav {
		width: 100%;
		display: flex;
		-webkit-box-pack: justify;
		-ms-flex-pack: justify;
		justify-content: space-between;
	}
	
	.main-nav ul li {
		margin: 0 20px;
	}
	.nav-phone-hide a{
		color: white;
	}
	
	.phone-menu {
		display: none;
		width: 100%;
		position: absolute;
		top: 60px;
		padding-bottom: 200%;
		background-color: rgba(0, 0, 0, .8);
	}
	
	.phone-menu li {
		text-align: center;
		height: 40px;
		line-height: 35px;
		font-size: 16px;
		background-color: white;
		color: #666;
		width: 100%;
		border-bottom: 1px solid #ddd;
	}
	
	@media screen and (max-width: 600px) {
		.nav-phone-show {
			font-size: 30px;
			cursor: pointer;
			display: inline-block;
		}
		.nav-phone-hide {
			display: none;
		}
		.phone-menu.active {
			display: block;
		}
	}
	
	@media screen and (min-width: 600px) {
		.nav-phone-show {
			display: none;
		}
		.nav-phone-hide {
			display: inline-block;
		}
		.phone-menu.active {
			display: none;
		}
	}
</style>