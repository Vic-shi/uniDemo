<template>
	<view>
		<view class="back">
			<view class="backHome" @click="backHome">
				<text>返回首页</text>
			</view>
			<view class="move">
				<view ref="lampView" v-bind:class="lampNow?'lampView':'lampView2'" class="" @click="lampStar">
					<view ref="lines" v-bind:class="lampNow?'lines':'lines2'">
						<view>
							<text></text>
							<text></text>
							<text></text>
							<text></text>
							<text></text>
						</view>
					</view>
					<text ref="lamp" v-bind:class="lampNow?'lamp':'lamp2'"></text>
				</view>
				<view class="thorax">
					<view class="header">
						<view class="eyes">
							<text></text>
							<text></text>
						</view>
						<view class="beard">
							<text></text>
							<text></text>
						</view>
					</view>
				</view>
				<view ref="wing" @click="lampStar" class="wing">
					<text v-bind:style="lampNow==true?'transform: rotate(30deg);':''"></text>
					<text v-bind:style="lampNow==true?'transform: rotate(-30deg);':''"></text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				lampNow:true
			}
		},
		onLoad() {

		},
		methods: {
			backHome:function(){
				window.history.back(-1)
			},
			lampStar:function(){
				
				if (this.lampNow == true) {
					this.lampNow = false
				} else {
					this.lampNow = true
				}
			}
		}
	}
</script>

<style>
	.thorax{
		background: #d43b1f;
		position: absolute;
		top: 150px;
		left: 0;
		right: 0;
		margin: auto;
		width: 50px;
		height: 35px;
		border-radius: 80% 80% 20% 20%;
		box-shadow: inset -0.1rem 0 0.1rem 0.3rem rgba(0, 0, 0, 0.2);
		z-index: 99;
	}
	.header{
		position: absolute;
		top: -5px;
		left: 0;
		right: 0;
		margin:auto;
		width: 70%;
		height: 50%;
		background: #27231e;
		border-radius: 80% 80% 40% 40%;
		/* box-shadow: inset -0.1rem 0 0 0.3rem rgba(14, 10, 10, 0.2); */
	}
	.eyes{
		display: flex;
		justify-content: space-between;
	}
	.eyes>text{
		display: block;
		height: 10px;
		width: 10px;
		background: #0e0a0a;
		border-radius: 100px;
	}
	.beard{
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		margin: auto;
	}
	.beard>text:first-child{
 		position: absolute;
		top: -45px;
		left: -85px;
		z-index: 9999999;
		display: block;
		height: 245px;
		width: 123px; 
		border-right:solid 2px #0e0a0a;
		border-top:solid 5px #0e0a0a;
		border-color:#0e0a0a transparent transparent transparent;
		border-radius: 50%/250px 260px 0 0;
		pointer-events: none;
	}
	.beard>text:nth-child(2){
 		position: absolute;
		top: -45px;
		left: -5px;
		z-index: 9999999;
		display: block;
		height: 245px;
		width: 125px; 
		border-left:solid 2px #0e0a0a;
		border-top:solid 5px #0e0a0a;
		border-color:#0e0a0a transparent transparent transparent;
		border-radius: 50%/250px 260px 0 0;
		pointer-events: none;
	}
	.wing,.wing2{
		position: absolute;
		top: 185px;
		height: 128px;
		width: 60px;
		left: 0;
		right: 0;
		margin: auto;
	}
	.wing>text,.wing2>text{
		width: 55%;
		height: 100%;
		display: block;
		position: absolute;
		top: 0;
		left: 0;
		z-index: 99;
		transition: all 200ms ease-out;
		background: repeating-linear-gradient(90deg,#27231e 0%, #27231e 40%, #191613 40%, #191613 60%);
		/* background: linear-gradient(90deg,#fb3  0%,#58a  40%,#58a  40%,#58a  60%); */
		/* background-size: 60px 100%; */
		border: 1px solid #40341d;
		box-sizing: border-box;
		box-shadow: inset 0 0 0.1rem 0.3rem rgba(0, 0, 0, 0.5);
	}
	.wing>text:first-child{
		transform-origin: top right;
		border-radius: 20% 0 30% 90%;
	}
	.wing>text:nth-child(2){
		transform-origin: top left;
		border-radius: 0 20% 90% 30%;
		left: 50%;
	}
	.wing2>text:first-child{
		border-radius: 20% 0 30% 90%;
	}
	.wing2>text:nth-child(2){
		left: 50%;
		border-radius: 0 20% 90% 30%;
	}
	.lines,.lines2{
		width: 90%;
		height: 150px;
		position: absolute;
		border-radius: 50%/50%;
		left: 0;
		right: 0;
		margin: auto;
		top: 0;
		overflow: hidden;
		box-shadow: rgba(0,0,0,0.1) 0px 0px 10px inset;
	}
	.lines>view,.lines2>view{
		width: 100%;
		height: 80%;
		position: absolute;
		left: 0;
		right: 0;
		margin: auto;
		top: 10%;
		display: flex;
		flex-flow: column;
		overflow: hidden;
		align-items: center;
		justify-content: space-between;
	}
	.lines>view>text{
		display: block;
		background: #e5e38b;
		height: 5px;
		width: 100%;
	}
	.lines2>view>text{
		display: block;
		background: black;
		height: 5px;
		width: 100%;
	}
	.lampView{
		width: 60px;
		height: 150px;
		background: #fffd99;
		border: 1px solid #fffd99;
		box-shadow: rgba(0,0,0,0.1) 0px 0px 10px inset;
		border-radius: 50%/50%;
		position: absolute;
		left: 0;
		right: 0;
		margin: auto;
		top: 150px;
		cursor: pointer;
		z-index: 99;
		animation: colorChange 4s infinite;
	}
	.lampView2{
		width: 60px;
		height: 150px;
		background: #1b1915;
		border: 1px solid #1b1915;
		box-shadow: #1b1915 0px 0px 10px inset;
		border-radius: 50%/50%;
		position: absolute;
		left: 0;
		right: 0;
		margin: auto;
		top: 150px;
		cursor: pointer;
		z-index: 99;
	}
	.lamp{
		display: block;
		width: 60px;
		height: 150px;
		border-radius: 50%/50%;
		box-shadow: #FFFF00 0px 0px 100px;
		position: absolute;
		left: 0;
		right: 0;
		margin: auto;
		top: 0;
		animation: bigSmall 4s infinite;
	}
	.lamp2{
		display: block;
		width: 150px;
		height: 60px;
		border-radius: 50%/50%;
		position: absolute;
		left: 0;
		right: 0;
		margin: auto;
		top: 0;
		animation: 4s;
	}
	@keyframes colorChange{
		0%{
			background: #fffd99;
		}
		50%{
			background: #fffd99;			
		}
		75%{
			background: #fefa0b;
		}
		100%{
			background: #fffd99;
		}
	}
	@keyframes bigSmall{
		0%{
			box-shadow: #FFFF00 0px 0px 100px
		}
		20%{
			box-shadow: #FFFF00 0px 0px 80px
		}
		40%{
			box-shadow: #FFFF00 0px 0px 100px
		}
		75%{
			box-shadow: #fefa0b 0px 0px 10px
		}
	}
	.back{
		background: radial-gradient(#0a2a43 30%, #09243a);
		height: 100vh;
		width: 100vw;
	}
	.move{
		height: 100vh;
		width: 100vw;
		position: absolute;
	}
</style>
