<template>
	<view>
		<cu-custom bgColor="bg-blue" :isBack="true">
			<block slot="backText">返回</block>
			<block slot="content">列表</block>
		</cu-custom>
		<image src="/static/map.jpg" class="map"></image>
		<view class="operation">
			<scroll-view scroll-x class="bg-white nav">
				<view class="flex text-center">
					<view class="cu-item flex-sub" :class="index==tabCur?'text-blue cur':''" v-for="(item,index) in tab" :key="index" @tap="tabSelect" :data-id="index">
						{{item.name}}
					</view>
				</view>
			</scroll-view>
			<scroll-view scroll-x class="bg-white nav">
				<view class="flex text-center">
					<view class="cu-item"  v-for="(item,index) in childrenTab" :key="index" @tap="childrenTabSelect" :data-id="index">
						<view class='cu-tag' :class="index==childrentabCur?'bg-blue':''" style="border-radius: 5px;">{{item.name}}</view>
					</view>
				</view>
			</scroll-view> 
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabCur: 0,
				childrentabCur: 0,
				tab:[
					{
						id:0,
						name:'降水',
						children:[
							{
								id:0,
								name:'当前',
							},
							{
								id:1,
								name:'最高',
							},
							{
								id:2,
								name:'最低',
							}
						]
					},
					{
						id:1,
						name:'风',
						children:[
							{
								id:0,
								name:'当前',
							},
							{
								id:1,
								name:'最高',
							},
							{
								id:2,
								name:'最低',
							}
						]
					},
					{
						id:2,
						name:'温度',
						children:[
							{
								id:0,
								name:'当前',
							},
							{
								id:1,
								name:'最高',
							},
							{
								id:2,
								name:'最低',
							}
						]
					},
					{
						id:3,
						name:'能见度',
						children:[
							{
								id:0,
								name:'当前',
							},
							{
								id:1,
								name:'最高',
							},
							{
								id:2,
								name:'最低',
							}
						]
					},
				],
				childrenTab:[]
			}
		},
		methods: {
			tabSelect(e) {
				this.tabCur = e.currentTarget.dataset.id;
				this.tab.forEach(item=>{
					if(item.id == e.currentTarget.dataset.id){
						this.childrenTab=item.children
					}	
				})
				this.childrentabCur=0;
				console.log('tab-id：'+this.tabCur)
			},
			childrenTabSelect(e){
				this.childrentabCur = e.currentTarget.dataset.id;
				console.log('children-tab-id：'+this.childrentabCur)
			}
		},
		mounted(){
			this.childrenTab=this.tab[0].children;
		}
	}
</script>

<style>
.map{
	width: 100%;
	height: 100vh;
	position: fixed;
	z-index: 1
}
.operation{
	position: absolute;
	z-index: 10;
	width: 100%;
}
</style>
