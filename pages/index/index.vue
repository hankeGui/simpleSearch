<template>
	<view class="content">
		<!-- status -->
		<view class="status"></view>
		<view class="main">
			<image class="logo" src="../../static/logo.png" mode=""></image>
			<view class="search">
				<input
				class="input"
				type="text" 
				@input="getInputValue"
				@blur="search"
				/>
				<text class="search-icon cuIcon-search" @tap="search()"></text>
			</view>
			<!-- 站点图标 -->
			<view class="site-box" v-if="siteVisiable">
				<view class="site" v-for="(item, index) in siteList" :key="index" @tap="goView(item.src)">
					<image class="site-img" :src="item.image"></image>
					<view class="site-name">
						{{item.title}}
					</view>
				</view>
			</view>
			
			<view v-if="resultVisiable">
				{{resultText}}
			</view>
		</view>
		<SetBar></SetBar>
		<BottomBar v-if="v"></BottomBar>
	</view>
</template>

<script>
	import SetBar from '../../components/SetBar/index.vue';
	import BottomBar from '../../components/BottomBar/index.vue'
	export default {
		components:{
			SetBar,
			BottomBar,
		},
		data() {
			return {
				v: false,
				searchEngine: 'https://www.baidu.com/s?wd=',
				siteList: '',
				inputValue: '',
				siteVisiable: false,
				resultVisiable: false,
				resultText:"",
			}
		},
		
		onLoad() {
			this.$store.commit('SHOWVIEWBAR', false);
			this.siteList = this.$store.state.siteList;
		},
		methods: {
			hiddSetBar(){
				this.$store.commit('SHOWBOTTOM', false);
			},
			goView(src){
				uni.navigateTo({
					url: '../view/view?src='+src
				})
			},
			getInputValue(e){
				this.inputValue = e.target.value;
			},
			search(){
				// var src = encodeURI(this.searchEngine + this.inputValue);
				// this.goView(src);
				this.showResult();
			},
			showResult(){
				this.resultText = this.inputValue + "未找到合适的结果";
				this.resultVisiable = true
				if(this.inputValue == "flip") {
					uni.navigateTo({
						url:'../view/Flip-Countdown'
					})
				} 
			}
		}
	}
</script>

<style>
	@import url("./index.css");
</style>
