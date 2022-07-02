<!--
 * @Description: 
 * @Author: lijiapeng
 * @Date: 2022-05-30 21:31:48
 * @LastEditTime: 2022-07-02 18:09:08
 * @LastEditors: lijiapeng
 * @Reference: 
-->
<template>
	<view class='index'>
    <IndexSwiper></IndexSwiper>
    <Recommend></Recommend>
    <Card cardTitle="猜你喜欢"></Card>
    <CommodityList></CommodityList>
    
    <Card cardTitle='热销爆品'></Card>
    		
    <Hot></Hot>

    <Card cardTitle='推荐店铺'></Card>

    <Shop></Shop>
    
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
		methods: {

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
</style>
