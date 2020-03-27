**uni-app 歌词显示组件**
+ 属性

    |参数|默认值|类型|说明|
    |:---|:---|:---|:---|
	|lyrics|[]|Array|需要展示的歌词，每句歌词中应该包含歌词展示的时间节点，时间放在一对"[]"里面，放在歌词的前面，如['[00:45.660]低着头 期待白昼','[00:50.740]接受所有的嘲讽','[00:56.010]向着风 拥抱彩虹','[01:01.700]勇敢的向前走'],时间格式可以是[时:分:秒:毫秒]或[时:分:秒]以及[秒]，后面两种格式毫秒部分以小数形式表示，如30秒500毫秒，表示为[30.5]|
	|curTime|0|Number|歌曲当前播放时间，以秒为单位|
	|lyricStyle|{color: "#000000" 歌词颜色,activeColor: '#ffffff' 当前播放的歌词的颜色,fontSize: '16px' 歌词字体尺寸,activeFontSize: '16px' 当前播放的歌词的字体尺寸,lineHeight: '40px' 每句歌词的显示区域的高度，以此来调整歌词间距,activeLineHeight: '32px' 当前播放歌词的显示区域的高度,selectedBGColor: 'inherit' 进入歌词选择模式时，被选择的歌词背景颜色}|Object|歌词显示风格设置|
	|areaStyle|width: '100vw' 歌词显示区域总宽,height: '70vh' 歌词显示区域总高,background: 'linear-gradient(#8cc8b4, #ffaa7f, #8cc8b4)' 歌词显示区域背景|Object|歌词显示区域设置，为了让每一句露头的歌词都完整显示，避免有歌词只显示一半的问题，因此对歌词实际显示高度做了调整，歌词全部显示高度可能会比设置高度小一点，但是整个组件的显示高度和属性设置中的一样|
	|centerStyle|btnImg: '' 左边按钮图片,btnText: 'btn' 左边按钮文本 设置btnImg时，此属性无效,color: '#ffffff' 文字和线条颜色,lineHeight: '1px' 中线的尺寸高度,height: '16px' 该区域的总高，如存在btnImg,他就是img的宽和高,fontSize: '14px' 该部分字体尺寸|Object|手指触摸滑动歌词时，在组件中心，会出现一条线，指示当前位于组件中心的歌词，并能够获取该歌词以及播放时间，可通过其扩展设置播放进度|
	|selectControlStyle|height: '40px' 工具条高度,backgroundColor: 'grey' 工具条背景颜色,itemFontSize: '16px' 选项字体尺寸,itemBorderRadius: '99px' 选项边框,itemBackgroundColor: '#00ffff' 选项背景颜色|Object|长按歌词进入歌词选择模式，点击复制歌词选项，通过监听copyLyrics事件，可获取选中的歌词|
	
	
+ 事件
	
    |名称|返回参数|说明|
    |:---|:---|:---|
	|copyLyrics|lyrics|Object类型，键： 歌词显示时间，单位秒； 值：歌词，长按歌词进入歌词选择模式，点击"复制歌词"返回的歌词信息|
	|centerBtnClick|centerTime: 点击按钮时，中心线选中的歌词显示时间，centerLyric：点击按钮时，中心线选中的歌词|触摸歌词显示区域滑动选择歌词，歌词显示中心出现的辅助选择控件，点击左侧按钮触发该事件|