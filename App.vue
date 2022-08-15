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
	@import url("colorui/icon.css");
	@import url("colorui/main.css");
	/*每个页面公共css */
	page{
		width: 100%;
		height: 100%;
	}
	.content{
		width: 100%;
		height: 100%;
		background-color: #FFFFFF;
	}
</style>

