<template>
  <div class='container'>
    <div class='myInfo'>
      <img class='peopleimage' :src='user.userPhoto'></img>
      <div class='peopleinfo'>
        <span class='peoplename'>{{user.userName}}
          <img class='peo-icon' src="/static/images/woman - anticon.png"></img>
        </span>
        <span class='peopleid'>ID: {{user.userId}}</span>
      </div>
      <span class='peoplePage' @click="viewPersonalPages">个人主页
        <img class='peo-icon' src="/static/images/Group 2@2x.png"></img>
     </span>
    </div>
    <div class="myTips">
      <van-cell-group >
        <van-cell title="我的送养" :border=false is-link link-type="navigateTo" size="large" url="/pages/mySongyang/main"/>
        <van-cell title="我收到的领养申请" :border=false is-link link-type="navigateTo" size="large" url="/pages/myReceiveApply/main"/>
        <van-cell title="我发起的领养申请" is-link link-type="navigateTo" size="large" url="/pages/index/index"/>
      </van-cell-group>
      <van-cell-group >
        <van-cell size="large" title="我的收藏" :border=false is-link link-type="navigateTo" url="/pages/myCollect/main"/>
        <van-cell size="large" title="我的关注" is-link link-type="navigateTo" url="/pages/myConcern/main"/>
      </van-cell-group>
      <van-cell-group >
        <van-cell size="large" title="我的资料" :border=false is-link link-type="navigateTo" url="/pages/myInfo/main"/>
        <van-cell size="large" title="我的答卷" is-link link-type="navigateTo" url="/pages/index/index"/>
      </van-cell-group>
      <van-cell-group >
        <van-cell size="large" title="帮助与反馈" :border=false is-link link-type="navigateTo" url="/pages/help/main"/>
        <van-cell size="large" title="推荐爪萌星给好友" is-link link-type="navigateTo" url="/pages/index/index"/>
      </van-cell-group>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        user: {
          userId: 123456,
          userPhoto: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
          userName: '白熊'
        }
      }
    },

    methods: {
      viewPersonalPages (e) {
        wx.navigateTo({
          url: '../myPages/main?id=' + this.user.userId
        })
      }
    }
  }
</script>

<style scoped>
  .myInfo {
     height:180rpx;
     background:rgba(255, 255, 255, 1);
     border-radius:16rpx;
     display:flex;
     position:relative;
   }
  .myTips {
    position:relative;
    width:100%;
    padding: 30rpx 30rpx;
  }
  .peo-icon {
    width: 20rpx;
    height: 20rpx;
    margin: 0 5rpx;
  }

  .peopleimage {
    width: 120rpx;
    height: 120rpx;
    border-radius: 50%;
    margin-top: 20rpx;
    margin-left: 30rpx;
    display: inline-block;
  }

  .peopleinfo {
    display: flex;
    display: inline-block;
    flex-direction: column;
    margin-top: 32rpx;
    margin-left: 20rpx;
    width: 500rpx;
  }

  .peoplename {
    font-size: 34rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(51, 62, 82, 1);
    display: block;
  }

  .peopleid {
    font-size: 26rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(131, 145, 168, 1);
    display: block;
  }
  .peoplePage {
    position: absolute;
    font-size: 28rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(186, 196, 209, 1);
    top: 32rpx;
    right: 30rpx;
  }
</style>
