<template>
  <div class='container'>
    <div class="helpBackGround"><image src="/static/images/Group 3.png"></image></div>
    <div class="helpInfo">
      <div class="headline">帮助与反馈</div>
      <div class="helpTips"><van-cell value-class="helpTipsText" custom-class="helpTipsDiv" value="若您遇到任何问题，请联系下方在线客服，我们竭诚为您服务。"/></div>
      <div class="helpContract">
        <div class="wxMa"><img src="https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640"></img></div>
        <div class="moreInfo">
          <div class="name">菠萝</div>
          <div class="moreTips">微信号/手机号</div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
  export default {
    data () {
      return {
        tag: true
      }
    },

    methods: {

    }
  }
</script>

<style scoped>
  .container {
    background-color: white;
    width: 100%;
    position: relative;
  }
  .helpBackGround{
    height: 623rpx;
    width: 100%;
  }
  .helpBackGround image{
    height: 623rpx;
    width: 100%;
  }
  .helpInfo{
    position: relative;
    display: flex;
    flex-direction: column;
    padding-left: 60rpx;
    padding-right: 60rpx;
    padding-top: 20rpx;
    padding-bottom: 140rpx;
  }
  .headline{
    font-size: 34rpx;
    font-weight: 500;
    font-family: PingFang SC Medium;
    color: #333E52;
    margin-top: 31rpx;
    margin-bottom: 30rpx;
  }
  .helpTips{
    font-size: 28rpx;
    font-family: PingFang SC Regular;
    color: #8391A8;

  }
  .helpContract{
    display: flex;
    margin-top: 34rpx;
    border-bottom: 2rpx solid #E6EAEF;;
  }
  .wxMa{
    height: 160rpx;
    width: 160rpx;
    border-radius: 8rpx;
    padding-bottom: 30rpx;
  }
  .wxMa img{
    height: 150rpx;
    width: 150rpx;
  }
  .moreInfo{
    display: flex;
    flex-direction: column;
    padding-left: 35rpx;
    padding-bottom: 23rpx;
    padding-top: 23rpx;
  }
  .moreInfo .name{
    font-size: 34rpx;
    font-family: PingFang SC Regular;
    color: #333E52;
  }
  .moreInfo .moreTips{
    font-size: 26rpx;
    font-family: PingFang SC Regular;
    color: #8391A8;
    padding-top: 20rpx;
  }
</style>
<style>
  .helpTipsDiv {
    padding: 0rpx !important;
  }
  .helpTipsText{
    text-align: left !important;
    padding-bottom: 30rpx !important;
  }
</style>
