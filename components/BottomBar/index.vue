<template name="BottomBar">
	<view class="bottom">
		<view class="menu">
			<text class="cuIcon-file"></text>
		</view>
		<view class="menu" @tap="showSetBar()">
			<text class="cuIcon-apps"></text>
		</view>
		<view class="menu">
			<view class="count">
				{{num}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"BottomBar",
		data (){
			return {
				num: 1,
			}
		},
		methods:{
			showSetBar(){
				this.$store.commit('SHOWBOTTOM', true);
			}
		}
	}
</script>

<style>
	@import url("./index.css");
</style>
