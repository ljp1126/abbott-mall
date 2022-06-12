<!--
 * @Description: 
 * @Author: lijiapeng
 * @Date: 2022-05-30 21:31:48
 * @LastEditTime: 2022-06-12 10:52:35
 * @LastEditors: lijiapeng
 * @Reference: 
-->
<template>
	<view class='index'>
    <IndexSwiper></IndexSwiper>
    <Recommend></Recommend>
    <Card cardTitle="猜你喜欢"></Card>
    <CommodityList></CommodityList>
	</view>
</template>


<script>
  import IndexSwiper from '@/components/index/IndexSwiper.vue'
  import Recommend from '@/components/index/Recommend.vue'
  import Card from '@/components/common/Card.vue'
  import CommodityList from '@/components/common/CommodityList.vue'
	export default {
		data() {
			return {
			
			}
		},
    components:{
      IndexSwiper,
      Recommend,
      Card,
      CommodityList
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
