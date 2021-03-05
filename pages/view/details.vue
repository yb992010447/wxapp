<template>
	<view class="content">
	  <view class="imgBox">
	  	<image src="../../static/logo.png" mode=""></image>
	  </view>
	  <view class="uploader-text" bindtap="doUpload">
	    <text>上传图片</text>
	  </view>
	  <view class="commentBox">
		<view class="commentItemBox" v-for="(item,index) in data" :key="index">
		  <view class="headerBox">
		  	<image class="img" :src=item.pimg mode=""></image>
			<text class="name">{{item.name}}</text>
			<text class="time">{{item.time}}</text>
		  </view>
		  <view class="comment">
		  	{{item.comment}}
		  </view>
		</view>
	  </view>
	  <view>
		<input confirm-type="search" @confirm="confirm" type="text" placeholder="请输入关键词" v-model="searchCont"/>
	  </view>
	</view>
</template>

<script>
	export default {
		data() {
		  return {
			searchCont:'',
			data:[
			  {
				pimg: '../../static/logo.png',
				name: '123',
				time: '2010/01/21',
				comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '456',
			  	time: '2010/10/21',
			  	comment: '大厦看就是打开的了大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  				pimg: '../../static/logo.png',
			  				name: '123',
			  				time: '2010/01/21',
			  				comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '456',
			  	time: '2010/10/21',
			  	comment: '大厦看就是打开的了大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  				pimg: '../../static/logo.png',
			  				name: '123',
			  				time: '2010/01/21',
			  				comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '456',
			  	time: '2010/10/21',
			  	comment: '大厦看就是打开的了大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  				pimg: '../../static/logo.png',
			  				name: '123',
			  				time: '2010/01/21',
			  				comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '456',
			  	time: '2010/10/21',
			  	comment: '大厦看就是打开的了大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  				pimg: '../../static/logo.png',
			  				name: '123',
			  				time: '2010/01/21',
			  				comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '456',
			  	time: '2010/10/21',
			  	comment: '大厦看就是打开的了大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  				pimg: '../../static/logo.png',
			  				name: '123',
			  				time: '2010/01/21',
			  				comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '456',
			  	time: '2010/10/21',
			  	comment: '大厦看就是打开的了大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  				pimg: '../../static/logo.png',
			  				name: '123',
			  				time: '2010/01/21',
			  				comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '456',
			  	time: '2010/10/21',
			  	comment: '大厦看就是打开的了大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  				pimg: '../../static/logo.png',
			  				name: '123',
			  				time: '2010/01/21',
			  				comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '456',
			  	time: '2010/10/21',
			  	comment: '大厦看就是打开的了大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '789',
			  	time: '2011/02/21',
			  	comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '234',
			  	time: '2010/05/20',
			  	comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '345',
			  	time: '2010/01/21',
			  	comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  },
			  {
			  	pimg: '../../static/logo.png',
			  	name: '567',
			  	time: '2010/01/21',
			  	comment: '大厦看就是打开的了哈链接坎大哈省联考的爱神的箭阿三大苏打大苏打实打实大苏打上时代卡洛斯；的卡了；速度看到了；ask的；阿斯顿'
			  }
			]
		  }
		},
		onLoad() {
		  console.log(12313)
		},
		methods: {
		  doUpload(){
			wx.chooseImage({
			  count: 1,
			  sizeType: ['compressed'],
			  sourceType: ['album', 'camera'],
			  success: function (res) {
			    wx.showLoading({
			      title: '上传中',
			    })
			
			    const filePath = res.tempFilePaths[0]
			    
			    // 上传图片
			    const cloudPath = `my-image${filePath.match(/\.[^.]+?$/)[0]}`
			    wx.cloud.uploadFile({
			      cloudPath,
			      filePath,
			      success: res => {
			        console.log('[上传文件] 成功：', res)
			
			        app.globalData.fileID = res.fileID
			        app.globalData.cloudPath = cloudPath
			        app.globalData.imagePath = filePath
			        
			        wx.navigateTo({
			          url: '../storageConsole/storageConsole'
			        })
			      },
			      fail: e => {
			        console.error('[上传文件] 失败：', e)
			        wx.showToast({
			          icon: 'none',
			          title: '上传失败',
			        })
			      },
			      complete: () => {
			        wx.hideLoading()
			      }
			    })
			  },
			  fail: e => {
			    console.error(e)
			  }
			})
		  },
		  confirm() {
		      //搜索的代码
		  },
		}
	}
</script>

<style>
.content {
  padding-left: 10px;
  padding-right: 10px;
  margin-bottom: 40px;
  display: flex;
  flex-direction: column;
}
.imgBox{
  width: 100%;
  height: 100%;
}
.uploader-text {
  margin-top: 20rpx;
}
.commentBox{}
.headerBox{
  margin-top: 20rpx;
}
.img{
  width: 30rpx;
  height: 30rpx;
  margin-right: 10rpx;
}
.name{
  
}
.time{
  float: right;
}
</style>
