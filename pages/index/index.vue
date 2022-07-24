<!--
 * @Description: 
 * @Author: lijiapeng
 * @Date: 2022-05-30 21:31:48
 * @LastEditTime: 2022-07-24 16:46:36
 * @LastEditors: lijiapeng
 * @Reference: 
-->
<template>
	<view class='index'>
    <scroll-view scroll-x="true" class='scroll-content' :scroll-into-view='scrollIntoIndex'>
			<view
				:id="'top'+index"
				class='scroll-item'
				v-for='(item,index) in topBar'
				:key='index'
				@tap='changeTab(index)'
			>
				<text :class='topBarIndex===index? " f-active-color" : "f-color"'>{{item.name}}</text>
			</view>
		</scroll-view>
		
		<swiper  @change='onChangeTab' :current="topBarIndex">
			<swiper-item 
				v-for='(item,index) in topBar'
				:key='index'
			>
				<view class='home-data'>
          <Banner></Banner>
					<Icons></Icons>
					<Card cardTitle='热销爆品'></Card>
					<Hot></Hot>
					<Card cardTitle='推荐店铺'></Card>
					<Shop></Shop>
					<Card cardTitle='为您推荐'></Card>
					<CommodityList></CommodityList>
        </view>
			</swiper-item>
		</swiper>


    <IndexSwiper></IndexSwiper>
    <Recommend></Recommend>
    <Card cardTitle="猜你喜欢"></Card>
    <CommodityList></CommodityList>
    
    <Card cardTitle='热销爆品'></Card>
    		
    <Hot></Hot>

    <Card cardTitle='推荐店铺'></Card>

    <Shop></Shop>

    <Card cardTitle='为你推荐'></Card>
    
    <Banner></Banner>
    <Icons></Icons>
	</view>
</template>


<script>
  import IndexSwiper from '@/components/index/IndexSwiper.vue'
  import Recommend from '@/components/index/Recommend.vue'
  import Card from '@/components/common/Card.vue'
  import CommodityList from '@/components/common/CommodityList.vue'
  import Banner from '@/components/index/Banner.vue'
  import Icons from '@/components/index/Icons.vue'
  import Hot from '@/components/index/Hot.vue'
  import Shop from '@/components/index/Shop.vue'
	export default {
		data() {
			return {
      //选中的索引
				topBarIndex:0,
				//顶栏跟随的索引id值
				scrollIntoIndex:'top0',
				//内容块的高度值
				clentHeight:0,
				//顶栏数据
				topBar:[
					{name:'推荐'},
					{name:'运动户外'},
					{name:'服饰内衣'},
					{name:'鞋靴箱包'},
					{name:'美妆个护'},
					{name:'家居数码'},
					{name:'食品母婴'}
				]
			}
		},
    components:{
      IndexSwiper,
      Recommend,
      Card,
      CommodityList,
      Banner,
      Icons,
      Hot,
      Shop
    },
		onLoad() {

		},
    onReady() {
			let view = uni.createSelectorQuery().select(".home-data");
			view.boundingClientRect(data => {
			    this.clentHeight = data.height;
			}).exec();
		},
		methods:{
			changeTab(index){
				if(this.topBarIndex === index){
					return ;
				}
				this.topBarIndex = index;
				this.scrollIntoIndex = 'top'+index;
			},
			onChangeTab(e){
				this.changeTab(e.detail.current);
			}
		}
	}
</script>

<style scoped>
.wx-nav{
	text-align: center;
	height: 200rpx;
	width:100%;
	line-height: 200rpx;
	/* display: flex; */
	/* justify-content: space-between; */
	/* align-items: center; */
}
.scroll-content{
	width: 100%;
	height: 80rpx;
	white-space: nowrap;
}
.scroll-item{
	display: inline-block;
	padding:10rpx 30rpx;
	font-size:32rpx;
}
.f-active-color{
	padding:10rpx 0;
	border-bottom: 6rpx solid #49BDFB;
}
</style>
