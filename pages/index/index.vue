<template>
	<view class="index">
		<text>首页</text>
		<text style="text-align: left;margin:0 0 5vw 10vw;font-size: 4vw;">展示列表</text>
		<view class="urlList">
			<view v-for="item in urlList" @click="goUrl(item.url)" :item='item.url'>
				<text>{{item.name}}</text>
			</view>
		</view>
		<image src="../../static/logo.png"></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				urlList:[{'name':'萤火虫',url:'../glowworm/index'},{'name':'跑动的小人',url:'../running/index'},{'name':'飘动的火箭',url:'../rocket/index'}]
			}
		},
		onLoad() {
	
		},
		methods: {
			goUrl:function(res){
				if(res){
					uni.navigateTo({
					    url: res
					});
				}
			}
		}
	}
</script>

<style>
	.index{
		text-align: center;
		font-size: 6vw;
		padding-top: 5vw;
	}
	.index>text{
		display: block;
	}
	.urlList{
		text-align: left;
		width: 80vw;
		margin: auto;
		font-size: 4vw;
	}
	.urlList>view{
		margin: 2vw 0;
		cursor: pointer;
	}
</style>
