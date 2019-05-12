<template>

	<div class="img">
		<div class="home">图书管理系统</div>
			<div class="box2" align="center">
				<el-row>
					<el-col :span="24">
						<div class="grid-content bg-purple-dark">用户名&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
							<el-input v-model="input" prop="username" placeholder="请输入用户名" class="user" ></el-input>
						</div>
					</el-col>
				</el-row>
			</div>
			<div class="box4" align="center">
				<el-row>
					<el-col :span="24">
						<div class="grid-content bg-purple-dark">登录密码&nbsp;&nbsp;
							<el-input v-model="input1" prop="password" placeholder="请输入登录密码" class="user"  type="password"></el-input>
						</div>
					</el-col>
				</el-row>
			</div>
		<div class="box3" align="center">
			<el-row>
				<el-col :span="24">
					<div class="grid-content bg-purple-dark">
						&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
						<el-button type="primary" @click="handleClick">登录</el-button>
						&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
						<el-button type="success">注册</el-button>
					</div>
				</el-col>
			</el-row>
		</div>
		<div class="box5" align="center">
			<el-carousel :interval="2000" type="card" height="250px">
				<el-carousel-item v-for="item in imgList" :key="item.id">
					<el-row>
						<el-col :span="24"><img ref="imgHeight" :src="item.src" /></el-col>
					</el-row>
				</el-carousel-item>
			</el-carousel>
		</div>
		<div class="box1">河北工程大学 联系方式:905966042</div>
	</div>
</template>

<script>
	export default {
		name: 'Home2',
		data() {
			return {
				
				input1: '',
				input: '',
				imgList: [{
						id: 0,
						src: require("../../../public/8.jpg")
					},
					{
						id: 1,
						src: require("../../../public/3.jpg")
					},
					{
						id: 2,
						src: require("../../../public/4.jpg")
					},
					{
						id: 3,
						src: require("../../../public/5.jpg")
					},
					{
						id: 4,
						src: require("../../../public/6.jpg")
					},
					{
						id: 5,
						src: require("../../../public/7.jpg")
					},

				]
			}
		},
		methods: {
			// 			open:function(){
			// 				this.$alert('登陆成功', '登录提示', {
			// 					confirmButtonText: '确定',
			// 					callback: action => {
			// 						this.$message({
			// 							type: 'info',
			// 							message: `action: ${ action }`
			// 						});
			// 					}
			// 				});
			// 			},
			
			handleClick: function() {
				if (this.input == 123 && this.input1 == 123)
					(   
						this.$message('恭喜你登陆成功'),
						this.$router.push({
							path: '/home3'
						})
					)
				else if (this.input == '' || this.input1 == '') {
					this.$message('账号密码不能为空')
				}
				 else {
					this.$message('账号密码错误')
				}
			}
		}
	}
</script>
<style>
	/* .button1{
			margin: 0px 20px;
		} */
	.body {
		text-align: center;
		font-size: 10px;
	}

	.box1 {
		font-size: .6rem;
	}

	.img {
		width: 100%;
		height: 100vh;
		margin: 0rem;
		text-align: center;
		background-size: cover;
		background-image: url(../../../public/11.jpg);
		background-repeat: no-repeat;
		background-position: center;
		background-attachment: fixed;
	}

	.header {
		height: 120px;
	}

	.home {
		font-size: 1rem;
		height: 120px;
		padding: 30px;
		/* font: 20px/10px; */
	}

	.grid-content {
		border-radius: 4px;
		min-height: 36px;
		font-size: .45rem;
	}

	.user {
		width: 15%;
	}

	.box2 {
		height: 70px;
		/* 	position: absolute;
		left: ; */
		vertical-align: bottom;
	}

	.box3 {
		height: 180px;
		vertical-align: center;
	}

	.box4 {
		height: 100px;
	}

	.box5 {
		height: 340px;
		width: 58%;
		margin: 0 auto;
	}


	.el-carousel__item:nth-child(2n) {
		background-color: #99a9bf;
	}

	.el-carousel__item:nth-child(2n+1) {
		background-color: #d3dce6;
	}
</style>
