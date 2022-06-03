<template>
	<view class='index'>
    
    <IndexSwiper></IndexSwiper>
		
	</view>
</template>


<script>
  import IndexSwiper from '@/components/index/IndexSwiper.vue'
	export default {
		data() {
			return {
			
			}
		},
    components:{
      IndexSwiper
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
