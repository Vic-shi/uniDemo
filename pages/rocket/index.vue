<template>
	<view class="background">
		<view class="backHome" @click="backHome">
			<text>返回首页</text>
		</view>
		<view class="rocket">
			<view class="body">
				<view class="header"></view>
			</view>
		</view>
		<view>
			{{text}}
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				text: ''
			}
		},
		onLoad() {
			uni.request({
			    url: 'http://47.240.253.19:8888/1233', //仅为示例，并非真实接口地址。
			    success: (res) => {
			        this.text = res.data;
			    }
			});
			
			
			
		},
		methods: {
			backHome:function(){
				window.history.back(-1)
			}
		}
	}
</script>

<style>
	.background{
		background: #1d1f20;
		width: 100vw;
		height: 100vh;
	}
	.rocket{
		margin: auto;
		text-align: center;
		padding:5vw 0 0 15vw;
	}
	.body{
		height: 25vw;
		width: 15vw;
		border-radius: 50% / 50%;
		background-color: #fff;
		transform: rotate3d(0, 0, 1, 40deg);
		position: relative;
	}
	.header{
		width: 8vw;
		height: 8vw;
		background: red;
		border-radius: 8vw;
		margin: auto;
	}
</style>
