<template name="ViewBar">
	<view class="view-bar" >
		<view class="bar" @tap.stop="goBack(s)">
			<text class="cuIcon-back"></text>
		</view>
		<view class="bar" @tap.stop="goForward()">
			<text class="cuIcon-right"></text>
		</view>
		<view class="bar" @tap.stop="showSetBar()">
			<text class="cuIcon-apps"></text>
		</view>
		<view class="bar">
			<view class="count">
				1
			</view>
		</view>
		<view class="bar">
			<text class="cuIcon-home" @tap.stop="goHome()"></text>
		</view>
	</view>
</template>

<script>
	export default {
		name: "ViewBar",
		data (){
			return {
				
			}
		},
		methods:{
			goBack(){
				history.back();
			},
			goForward(){
				history.forward()
			},
			showSetBar(){
				this.$store.commit('SHOWBOTTOM', true);
			},
			goHome(){
				uni.navigateTo({
					url: '../../pages/index/index'
				})
			}
		}
	}
</script>

<style>
	@import url("./index.css");
</style>

