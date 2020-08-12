<template>
	<div class="home">
		<!-- 头 -->
		<div class="header">
			<el-row class="container">
				<el-col :xs="24" :sm="12" :md="12" class="logo">
					<img src="../assets/home_03.jpg" alt="logo">
					<span>北京站</span>
					<div class="back-img" @click="navStavte()"></div>
				</el-col>
				<el-col :xs="24" :sm="12" :md="12" class="nav none" :class='{nav_active:navStavteIndex==1}'>
					<div class="active">首页</div>
					<div>找职位</div>
					<div>找精英</div>
					<div>关于我们</div>
				</el-col>
			</el-row>
		</div>
		<!-- 轮播图 -->
		<div class="rotation">
			<div class="container">
				<img src="../assets/home_06.jpg" alt="轮播图">
			</div>
		</div>
	</div>
</template>

<script>
	// @ is an alias to /src
	// import HelloWorld from '@/components/HelloWorld.vue'

	export default {
		name: 'Home',
		components: {
			// HelloWorld
		},
		data() {
			return {
				navStavteIndex: 0
			}
		},
		methods: {
			navStavte() {
				if (this.navStavteIndex == 1) {
					this.navStavteIndex = 0;
				} else {
					this.navStavteIndex = 1;
				}

			}
		}
	}
</script>
<style scoped lang="scss">
	// 公共
	.container {
		margin: 0 auto;
		padding: 0;
		max-width: 1024px;
		height: 100%;
	}

	// 头
	.header {
		margin: 0;
		padding: 0;
		height: 80px;
		background-color: #ffffff;

		.logo {
			display: flex;
			align-items: center;
			height: 80px;
			font-size: 16px;

			img {
				width: 308px;
				height: 40px;
				margin-right: 10px;
			}
		}

		.nav {
			display: flex;
			align-items: center;
			justify-content: flex-end;
			height: 100%;

			div {
				padding: 0 12px;
				height: 80px;
				display: flex;
				align-items: center;
				justify-content: center;
				font-size: 16px;
				background-color: #ffffff;
				border-bottom: 2px solid #ffffff;
			}

			div:hover {
				border-bottom: 2px solid red;
			}

			.active {
				border-bottom: 2px solid red;
			}
		}
	}

	@media screen and (max-width: 768px) {
		.back-img {
			position: absolute;
			right: 20px;
			width: 55px;
			height: 43px;
			border-radius: 8px;
			background-image: url(../assets/menu.png);
			background-size: 100% 100%;
		}

		.nav {
			height: 0px !important;
			overflow: hidden;
			display: block !important;
			transition: height 1s;

			div {
				width: 100%;
			}
		}

		.nav_active {
			height: 330px !important;
		}
	}




















	// 录播图
	.rotation {
		height: auto;
		max-height: 500px;
		background-color: #f6f7f8;
		img {
			width: 100%;
			height: 100%;
		}
	}
</style>
