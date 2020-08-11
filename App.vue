<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	uni-page-head{
		display: none;
	}
	.allButton{
		width: 50vw;
	}
	.backHome{
		padding: 5vw 0 0 5vw;
	}
	.backHome>text{
		color: #ffffff;
	}
</style>
