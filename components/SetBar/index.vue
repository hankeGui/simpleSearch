<template name="SetBar">
	<view class="setbar" v-show="this.$store.state.ifShowBottom">
		<view class="set-opt">
			<view class="opt">
				<text class="cuIcon-refresh"></text>
				<view class="opt-name">
					刷新
				</view>
			</view>
			<view class="opt">
				<text class="cuIcon-favor"></text>
				<view class="opt-name">
					收藏
				</view>
			</view>
			<view class="opt">
				<text class="cuIcon-send"></text>
				<view class="opt-name">
					收藏夹
				</view>
			</view>
			<view class="opt">
				<text class="cuIcon-countdown"></text>
				<view class="opt-name">
					历史
				</view>
			</view>
			<view class="opt">
				<text class="cuIcon-share"></text>
				<view class="opt-name">
					分享
				</view>
			</view>
			<view class="opt">
				<text class="cuIcon-footprint"></text>
				<view class="opt-name">
					无痕
				</view>
			</view>
			<view class="opt">
				<text class="cuIcon-pulldown"></text>
				<view class="opt-name">
					下载
				</view>
			</view>
			<view class="opt">
				<text class="cuIcon-repair"></text>
				<view class="opt-name">
					工具箱
				</view>
			</view>
			<view class="opt">
				<text class="cuIcon-creative"></text>
				<view class="opt-name">
					夜间模式
				</view>
			</view>
			<view class="opt">
				<text class="cuIcon-settings"></text>
				<view class="opt-name">
					设置
				</view>
			</view>
		</view>
		<view class="set-close">
			<text class="cuIcon-close" @tap="hideBottom()"></text>
		</view>
	</view>

</template>

<script>
	export default {
		name: "SetBar",
		data () {
			return {
				
			}
		},
		methods:{
			hideBottom(){
				this.$store.commit('SHOWBOTTOM', false);
			},
		}
	}
</script>

<style>
	@import url("./index.css");
</style>
