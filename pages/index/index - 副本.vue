<template>
	<view class="content">
		<text>top</text>
		<!-- <bing-lyric class="lyric" v-if="lyrics.length > 0" :lyrics="lyrics" :curTime="curTime"></bing-lyric> -->
		<scroll-view id="lyric-show" class="lyric-show" @tap="convert" scroll-y="true" :scroll-into-view="curLyricId" @scroll="lyricScroll">
			<view v-for="(v, i) in lyrics" :key="i">
				<text selectable="true" :class="curLyricIndex == i ? 'curLyric' : ''" :id="'a' + i">{{v}}</text>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	import bingLyric from "../../components/bing-lyric/bing-lyric.vue"
	export default {
		components: {
			bingLyric
		},
		data() {
			return {
				title: 'Hello',
				lyrics: ['[00:00.000] 作曲 : 刘涛',
						'[00:01.000] 作词 : 林晨阳 /刘涛',
						'[00:11.790]编曲 Arranger：谭侃侃',
						'[00:24.940]也许世界就这样',
						'[00:28.190]我也还在路上',
						'[00:30.830]没有人能诉说',
						'[00:35.910]也许我只能沉默',
						'[00:38.950]眼泪湿润眼眶',
						'[00:41.800]可又不甘懦弱',
						'[00:45.660]低着头 期待白昼',
						'[00:50.740]接受所有的嘲讽',
						'[00:56.010]向着风 拥抱彩虹',
						'[01:01.700]勇敢的向前走',
						'[01:06.379]黎明的那道光',
						'[01:08.810]会越过黑暗',
						'[01:11.450]打破一切恐惧我能',
						'[01:14.500]找到答案',
						'[01:17.140]哪怕要逆着光',
						'[01:19.580]就驱散黑暗',
						'[01:22.220]丢弃所有的负担',
						'[01:25.470]不再孤单',
						'[01:28.310]不再孤单'],
				curTime: 0,
			}
		},
		onLoad() {
			this.makeTime()
		},
		methods: {
			makeTime() {
				let i = 0
				// setTimeout(()=> this.lyrics=["[00:11.790]编曲 Arranger：谭侃侃", "[00:24.940]也许世界就这样",],2000)
				for (i;i<1000;i++){
					setTimeout((t)=>this.curTime = t, i*200,i)
				}
			}
		}
	}
</script>

<style>
	.content {
/* 		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center; */
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
	.lyric{
		position: absolute;
		top: 0;left: 0;
		border: #4CD964 solid 2px;
	}
	.lyric-show {
		align-items: center;
		text-align: center;
		width: 100vw;
		height: calc(100vh - var(--status-bar-height) - 350rpx);
		white-space: nowrap;
		overflow-x: hidden;
		background-image: linear-gradient(#8cc8b4, #ffaa7f, #8cc8b4);
		background-color: hsla(120, 100%, 75%, 0);
	}
	.lyric-show view{
		align-items: center;
		height: 60rpx;
		width: 100vw;
		font-size: 30rpx;
		white-space: nowrap;
		justify-content: center;
		padding: 10rpx;
	}
</style>
