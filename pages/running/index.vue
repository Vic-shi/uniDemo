<template>
	<view class="running">
		<view class="backHome" @click="backHome">
			<text>返回首页</text>
		</view>
		<view ref='person' class="person">
			<view class="header">
				<view class="hat">
					<view></view>
					<view></view>
				</view>
				<view class="face"></view>
			</view>
			<view class="leftHand"></view>
			<view class="rightHand"></view>
			<view class="body"></view>
			<view class="leftFoot"></view>
			<view class="rightFoot"></view>			
		</view>
		<view class="support"></view>
		<button class="allButton" @click="runningStart">{{runnnigName}}</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				runnnigName:'开始跑步'
			}
		},
		onLoad() {
	
		},
		methods: {
			backHome:function(){
				window.history.back(-1)
			},
			runningStart:function(){
				if(this.runnnigName === '开始跑步'){
					this.runnnigName === '停止跑步'
					this.$refs.person.$el.className = 'personRun'
				}else{
					this.runnnigName === '开始跑步'
					this.$refs.person.$el.className = 'person'
				}
			}
		}
	}
</script>

<style>
	.running{
		background: #1d1f20;
		width: 100vw;
		height: 100vh;
	}
	.support{
		height: 50vw;
		width: 100vw;
	}
	.person{
		position: absolute;
		left: 10vw;
		top: 20vw;
		display: inline-block;
	}
	.personRun{
		position: absolute;
		left: 10vw;
		top: 20vw;
		animation: personMove 3s infinite;
	}
	.header{
		animation: faceMove 1s infinite alternate;
		transform-origin: 50% 100% 0px;
	}
	.hat{
		text-align: center;
	}
	.hat>view:first-child{
		height: 0px;
		width: 6px;
		background: #fff;
		margin: auto;
		border-top-left-radius:2px;
		border-top-right-radius:2px;
		border-bottom: 6px solid transparent;
		border-left: 3px solid transparent;
		border-right: 3px solid transparent;
	}
	.hat>view:nth-child(2){
		height: 3px;
		width: 20px;
		border-radius: 3px;
		background: #fff;
	}
	.face{
		height: 10px;
		width: 15px;
		border:1px solid #fff;
		border-radius: 0 0 10px 10px;
		margin: auto;
	}
	.leftHand{
		transform:rotate(65deg);
		height: 15px;
		width: 15px;
		border-bottom: 1px solid #fff;
		border-left: 1px solid #fff;
		position: absolute;
		top: 26px;
		left: 9px;
		transform-origin: 0% 0% 0px;
		animation: leftHandMove 1s infinite ease-in-out;
	}
	.rightHand{
		transform:rotate(-45deg);
		height: 15px;
		width: 15px;
		border-bottom: 1px solid #fff;
		border-left: 1px solid #fff;
		position: absolute;
		left: 10px;
		top: 25px;
		transform-origin: 0% 0% 0px;
		animation: rightHandMove 1s infinite ease-in-out;
	}
	.body{
		width: .5px;
		height: 20px;
		background: #fff;
		position: absolute;
		left: 10px;
		top: 25px;
	}
	.leftFoot{
		transform:rotate(125deg);
		height: 20px;
		width: 20px;
		border-top: 1px solid #fff;
		border-right: 1px solid #fff;
		position: absolute;
		left: 10px;
		top: 45px;
		transform-origin: 0% 0% 0px;
		animation: leftFootMove 1s infinite ease-in-out;
	}
	.rightFoot{
		transform:rotate(-20deg);
		height: 20px;
		width: 20px;
		border-top: 1px solid #fff;
		border-right: 1px solid #fff;
		position: absolute;
		left: 10px;
		top: 45px;
		transform-origin: 0% 0% 0px;
		animation: rightFootMove 1s infinite ease-in-out;
	}
	@keyframes faceMove{
		0%{
			transform: rotate3d(0, 0, 1, -15deg);
		}
		50%{
			transform: rotate3d(0, 0, 1, 15deg);
		}
		100%{
			transform: rotate3d(0, 0, 1, -15deg);
		}
	}
	@keyframes leftHandMove{
		0%{
			transform: rotate3d(0, 0, 1, 80deg);
		}
		50%{
			transform: rotate3d(0, 0, 1, -70deg);
		}
		100%{
			transform: rotate3d(0, 0, 1, 80deg);
		}
	}
	@keyframes rightHandMove{
		0%{
			transform: rotate3d(0, 0, 1, -70deg);
		}
		50%{
			transform: rotate3d(0, 0, 1, 80deg);
		}
		100%{
			transform: rotate3d(0, 0, 1, -70deg);
		}
	}
	@keyframes leftFootMove{
		0%{
			transform: rotate3d(0, 0, 1, -5deg);
		}
		50%{
			transform: rotate3d(0, 0, 1, 150deg);
		}
		100%{
			transform: rotate3d(0, 0, 1, -5deg);
		}
	}
	@keyframes rightFootMove{
		0%{
			transform: rotate3d(0, 0, 1, 150deg);
		}
		50%{
			transform: rotate3d(0, 0, 1, -5deg);
		}
		100%{
			transform: rotate3d(0, 0, 1, 150deg);
		}
	}
	@keyframes personMove{
		0%{
			left: 10vw;
		}
		100%{
			left: 120vw;
		}
	}
</style>
