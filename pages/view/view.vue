<template>
	<view class="content">
		<!-- status -->
		<view class="status" ></view>
		<view class="main" >
			<web-view 
			class="view-bar"
			:src="src"
			webview-styles="false"
			@touchmove="showViewBar()"
			></web-view>
		</view>
		<SetBar></SetBar>
		<ViewBar v-show="ifShowViewBar"></ViewBar>
	</view>
</template> 

<script>
	import SetBar from '../../components/SetBar/index.vue';
	import ViewBar from '../../components/ViewBar/index.vue'
	export default {
		components:{
			SetBar,
			ViewBar,
		},
		data() {
			return {
				ifShowViewBar: true,
				src: ''
			}
		},
		onLoad(opt) {
			this.src = opt.src;
		},
		methods: {
			showViewBar(){
				this.$store.commit(SHOWVIEWBAR, !this.$store.state.ifShowViewBar);
			}
		}
	}
</script>

<style>
	@import url("./index.css");
</style>
