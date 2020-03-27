<template>
	<view class="content">
		<text>top</text>
		<bing-lyric :lyrics="lyrics" :centerStyle="centerStyle" :curTime="curTime" :areaStyle="cuAreaStyle" :lyricStyle="lyricStyle"
		 @centerBtnClick="centerBtnClick" @copyLyrics="copy"></bing-lyric>
		 <text>bottom</text>
	</view>
</template>

<script>
	import bingLyric from '../../components/bing-lyric/bing-lyric.vue'
	export default {
		components:{
			bingLyric
		},
		data() {
			return {
				title: 'Hello',
				centerStyle: {
					btnImg: '../../static/btn.png',
				},
				lyricStyle: {
				},
				cuAreaStyle: {
					width: '100vw',
				},
				lyrics: ['[0] 作曲 : 刘涛',
						'[1] 作词 : 林晨阳 /刘涛',
						'[2] 作词 : 林晨阳 /刘涛',
						'[3] 作词 : 林晨阳 /刘涛',
						'[00:04.000] 作词 : 林晨阳 /刘涛',
						'[00:05.000] 作词 : 林晨阳 /刘涛',
						'[00:06.000] 作词 : 林晨阳 /刘涛',
						'[00:07.000] 作词 : 林晨阳 /刘涛',
						'[00:08.000] 作词 : 林晨阳 /刘涛',
						'[00:09.000] 作词 : 林晨阳 /刘涛',
						'[00:10.000] 作词 : 林晨阳 /刘涛',
						'[00:11.000] 作词 : 林晨阳 /刘涛',
						'[00:11.790]编曲 Arranger：谭侃侃',
						'[00:12.790]编曲 Arranger：谭侃侃',
						'[00:13.790]编曲 Arranger：谭侃侃',
						'[00:14.790]编曲 Arranger：谭侃侃',
						'[00:15.790]编曲 Arranger：谭侃侃',
						'[00:16.790]编曲 Arranger：谭侃侃',
						'[00:17.790]编曲 Arranger：谭侃侃',
						'[00:18.790]编曲 Arranger：谭侃侃',
						'[00:19.790]编曲 Arranger：谭侃侃',
						'[00:20.940]也许世界就这样',
						'[00:22.940]也许世界就这样',
						'[00:25.940]也许世界就这样',
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
			copy(e){
				console.log('index',e)
				uni.showModal({
					content: JSON.stringify(e.lyrics)
				})
			},
			centerBtnClick(e){
				console.log(e)
				this.curTime = e.centerTime
			},
			makeTime() {
				let i = 0
				for (i;i<500;i++){
					setTimeout(this.out, i*500,0.5)
				}
			},
			out(t){
				this.curTime += t
			}
		}
	}
</script>
	
<style>
	.content{
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>
