<template name="topImg">
  <view class="home">
	<swiper
	  indicator-dots 	
	  circular
	  autoplay
	  interval=3000
	  >
		<swiper-item v-for="(item,index) in swipers" :key="index">
		  <image :src="item"></image>
		</swiper-item>
	</swiper>
  </view>
</template>

<script>
  export default {
	name: 'topImg',
	data() {
	  return {
		swipers: []
	  }
	},
	created() {
	  this.swipers = ['../../static/1.jpg', '../../static/2.jpeg', '../../static/3.jpg']
	},
	methods: {
			
	}
  }
</script>

<style>
.home{
  width: 100%;
  height: 100%;
}
image {
  width: 100%;
  height: 100%;
}
</style>
