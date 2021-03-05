<template>
  <view class="layout">
	<view class="search" @click="search">
		<icon type="search" size="16" color="#000"/>
		<view style="width: 200px;height: 32rpx;"></view>
	</view>
	<topImg class="banner"></topImg>
	<scroll-view class="nav" scroll-x="true">
	    <view
		  v-for="(item, index) in navs"
		  :key="index" 
		  :class="[index == tabCur ? 'ct_active navitem' : 'navitem']" 
		  @click="clickNavItems(index)"
		>
		  {{item}}
		</view>
	</scroll-view>
	<view class="content">
	  <view class="itemBox" v-for="(item, index) in data1" :key='index' @click="details">
	  	
	  </view>
	</view>
  </view>
</template>

<script>
  import topImg from '../components/topImg.vue'
  export default {
	name: 'index',
	components:{
	  topImg
	},
	data() {
	  return {
		data1:[
		  {
			month: '一月',
			commentNum: 999,
			uploadNum: 666
		  },
		  {
		  	month: '二月',
		  	commentNum: 999,
		  	uploadNum: 666
		  },
		  {
		  	month: '三月',
		  	commentNum: 999,
		  	uploadNum: 666
		  },
		  {
		  	month: '四月',
		  	commentNum: 999,
		  	uploadNum: 666
		  },
		  {
		  	month: '五月',
		  	commentNum: 999,
		  	uploadNum: 666
		  },
		  {
		  	month: '六月',
		  	commentNum: 999,
		  	uploadNum: 666
		  },
		  {
			month: '七月',
			commentNum: 999,
			uploadNum: 666
		  },
		  {
		  	month: '八月',
		  	commentNum: 999,
		  	uploadNum: 666
		  },
		  {
		  	month: '九月',
		  	commentNum: 999,
		  	uploadNum: 666
		  },
		  {
		  	month: '十月',
		  	commentNum: 999,
		  	uploadNum: 666
		  },
		  {
		  	month: '十一月',
		  	commentNum: 999,
		  	uploadNum: 666
		  },
		  {
		  	month: '十二月',
		  	commentNum: 999,
		  	uploadNum: 666
		  }
		  
		],
		navs: [],
		tabCur: 0
	  }
	},
	onLoad() {
	  this.navs = ['最新','一月','二月','三月','四月','五月','六月','七月','八月','九月','十月','十一月','十二月'],
	  uni.getUserInfo({
		success: (res) => {
		  this.userInfo = res.userInfo;
		  console.log(this.userInfo);
		},
	    fail: () => {
		  console.log("未授权");
		}
	  })
	},
	methods: {
	  search() {
		wx.navigateTo({
		  url: '../search/search'
		})
	  },
	  clickNavItems(index) {
		this.tabCur = index
	  },
	  details() {
		console.log('触发了一个手指点击事件')
		wx.navigateTo({
		  url: '../view/details'
		})
	  }
	}
  }
</script>

<style>
.layout {
  display: flex;
  flex-direction: column;
  width: 100%;
}
.search{
  margin: 20rpx;
  padding: 20rpx;
  display: flex;
  background-color: #C0C0C0;
}
.banner{
  height: 20%;
  margin: 0 20rpx;
}
.nav{
  width: 100%;
  margin: 0 20rpx;
  margin-top: 20rpx;
  font-weight: bold;
  color: #c0c8d0;
  white-space: nowrap;
  overflow: hidden;
}
.navitem{
  width: 60px;
  border-right: 1px solid red;
  text-align: center;
  display: inline-block;
}
.navitem:last-child{
   padding-right: 30rpx;
}
.ct_active{
    color:#FFFFFF;
}
.content {
  flex: 1;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  margin-left: 20rpx;
  margin-right: 20rpx;
  margin-bottom: 50rpx;
}
.itemBox {
  width: 48%;
  height: 450rpx;
  margin-top: 20rpx;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background-color: #fff;
}
.bottomBorder{
  border-bottom: 1px solid #007AFF;
}
.imgBox {
  width: 100%;
  height: 50%;
}

.buttonBox {
  width: 90%;
  display: flex;
  margin:0 auto;
  justify-content: space-between;
}
</style>
