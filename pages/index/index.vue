<template name="components">
	<view>
		<image src="/static/bj.jpg" mode="widthFix" class="response"></image>
		<scroll-view scroll-y class="page">
			<view class="cu-card case">
				<view class="cu-item shadow" style="margin-bottom: 0rpx;">
					<view class="cu-bar">
						<view class="action">
							<text class="cuIcon-title text-orange "></text> 高空观测
						</view>
					</view>
					<view class="cu-list grid col-4 no-border">
						<view class="cu-item" v-for="(item,index) in highObservation" :key="index">
							<view class="iconfont cuIcon-cuIcon" :class="[item.cuIcon,'text-' + item.color]"></view>
							<text>{{item.name}}</text>
						</view>
					</view>
				</view>
			</view>
			
			<view class="cu-card case">
				<view class="cu-item shadow" style="margin-bottom: 0rpx;">
					<view class="cu-bar bg-white">
						<view class="action">
							<text class="cuIcon-title text-orange "></text> 地面观测
						</view>
					</view>
					<view class="cu-list grid col-4 no-border">
						<view class="cu-item" v-for="(item,index) in groundObservation" :key="index">
							<view class="iconfont cuIcon-cuIcon" :class="[item.cuIcon,'text-' + item.color]"></view>
							<text>{{item.name}}</text>
						</view>
					</view>
				</view>
			</view>
			
			<view class="cu-card case">
				<view class="cu-item shadow" style="margin-bottom: 0rpx;">
					<view class="cu-bar bg-white">
						<view class="action">
							<text class="cuIcon-title text-orange "></text> 睿图产品
						</view>
					</view>
					<view class="cu-list grid col-3 no-border">
						<view class="cu-item" v-for="(item,index) in ruituProducts" :key="index">
							<view class="iconfont cuIcon-cuIcon" :class="[item.cuIcon,'text-' + item.color]"></view>
							<text>{{item.name}}</text>
						</view>
					</view>
				</view>
			</view>
			
			<view class="cu-card case">
				<view class="cu-item shadow" style="margin-bottom: 0rpx;">
					<view class="cu-bar bg-white">
						<view class="action">
							<text class="cuIcon-title text-orange "></text> 预报产品
						</view>
					</view>
					<view class="cu-list menu sm-border">
						<view class="cu-item" v-for="(item,index) in forecastProducts" :key="index">
							<navigator class="content" hover-class="none" :url="item.url" open-type="redirect">
								<text class="iconfont cuIcon-cuIcon" :class="[item.cuIcon,'text-' + item.color]"></text>
								<text class="text-grey">{{item.name}}</text>
							</navigator>
						</view>
					</view>
				</view>
			</view>
			
			<view class="cu-card case">
				<view class="cu-item shadow" style="margin-bottom: 0rpx;">
					<view class="cu-bar bg-white">
						<view class="action">
							<text class="cuIcon-title text-orange "></text> 服务产品
						</view>
					</view>
					<view class="cu-list menu sm-border">
						<view class="cu-item" v-for="(item,index) in serviceProducts" :key="index">
							<navigator class="content" hover-class="none" :url="item.url" open-type="redirect">
								<text class="iconfont cuIcon-cuIcon" :class="[item.cuIcon,'text-' + item.color]"></text>
								<text class="text-grey">{{item.name}}</text>
							</navigator>
						</view>
					</view>
				</view>
			</view>
			
			<view class="cu-card case">
				<view class="cu-item shadow">
					<view class="cu-bar bg-white">
						<view class="action">
							<text class="cuIcon-title text-orange "></text> 全球数值
						</view>
					</view>
					<view class="cu-list grid col-2 no-border">
						<view class="cu-item" v-for="(item,index) in globalValue" :key="index">
							<view class="iconfont cuIcon-cuIcon" :class="[item.cuIcon,'text-' + item.color]"></view>
							<text>{{item.name}}</text>
						</view>
					</view>
				</view>
			</view>
			
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				highObservation: [
					{
						cuIcon: 'iconleida',
						color: 'red',
						name: '雷达回波'
					}, {
						cuIcon: 'icontankong',
						color: 'orange',
						name: '探空'
					}, {
						cuIcon: 'iconshandian',
						color: 'yellow',
						name: '闪电'
					}, {
						cuIcon: 'iconyuntu',
						color: 'olive',
						name: '云图'
					}
				],
				groundObservation: [
					{
						cuIcon: 'iconshikuang',
						color: 'red',
						name: '天气实况'
					}, {
						cuIcon: 'iconturang',
						color: 'orange',
						name: '土壤'
					}, {
						cuIcon: 'icondaomianzhan',
						color: 'yellow',
						name: '道面站'
					}, {
						cuIcon: 'iconhuanjing',
						color: 'olive',
						name: '环境'
					}
				],
				ruituProducts: [
					{
						cuIcon: 'iconin',
						color: 'red',
						name: 'RMAPS-IN'
					}, {
						cuIcon: 'iconin',
						color: 'orange',
						name: 'RMAPS-NOW'
					}, {
						cuIcon: 'iconin',
						color: 'yellow',
						name: 'RMAPS-ST-3H'
					}
				],
				
				forecastProducts: [
					{
						cuIcon: 'iconbaogao',
						color: 'red',
						name: '天气公报'
					}, {
						cuIcon: 'iconzhoubian',
						color: 'orange',
						name: '周边天气预报'
					}, {
						cuIcon: 'iconshijian',
						color: 'yellow',
						name: '未来240h小时预报'
					}, {
						cuIcon: 'iconshijian',
						color: 'yellow',
						name: '未来12h小时预报'
					}
				],
				
				serviceProducts: [
					{
						cuIcon: 'iconbaogao',
						color: 'red',
						name: '天气情况'
					}, {
						cuIcon: 'iconbaogao',
						color: 'orange',
						name: '天气快报'
					}, {
						cuIcon: 'iconbaogao',
						color: 'yellow',
						name: '重要天气报告'
					}, {
						cuIcon: 'iconzhoubian',
						color: 'yellow',
						name: '雨（雪）量实况表DOC'
					}
				],
				
				globalValue: [
					{
						cuIcon: 'iconin',
						color: 'red',
						name: 'EC_thin'
					}, {
						cuIcon: 'iconin',
						color: 'orange',
						name: 'Grapes预报'
					}
				],
			};
		}
	}
</script>

<style>
	.page {
		/* height: calc(100vh - 280px); */
	}
</style>
