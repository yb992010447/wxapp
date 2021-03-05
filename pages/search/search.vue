<template>
   <view class="searchBox">
	   <view class="topBox">
		  <input class="inputbox" type="text" :value="searchValue" focus="true" />
		  <view @click="goBack">取消</view>
	   </view>
   </view>
</template>

<script>
  export default {
  	name: 'search',
  	data() {
  	  return {
		searchValue:''
  	  }
  	},
  	created() {
  		
  	},
  	methods: {
  	  goBack() {
		wx.navigateBack({
		  success: function() {
			index.onLoad(); // 执行前一个页面的onLoad方法
		  }
		});
	  }
  	}
  }
</script>

<style>
.searchBox{
   width: 100%;
   height: 100%;
   background-color: #FFFFFF;
   padding: 0 10rpx;
}
.topBox{
   display: flex;
   padding-top: 10rpx;
   margin: 0 10rpx;
}
.inputbox{
   width: 80%;
   background-color: #C8C7CC;
}
</style>
