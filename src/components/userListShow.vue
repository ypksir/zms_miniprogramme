<template>
  <div @tap="onTap" class="container">
    <img class='userimg' :src="user.image"></img>
    <div class="description">
      <div class='name'><div class='nametitle'>{{user.name}}</div><img src="/static/images/woman - anticon.png" /></div>
      <div class='moretip'>
        <div class='age'>{{user.city}} | {{user.year}}</div>
        <div class='sending'>待送养:  {{user.sending}}</div>
      </div>
      <div class="dataTips">
        <div class='sended'>已送养:  {{user.sended}}</div>
        <div class='geted'>已领养:  {{user.geted}}</div>

        <div class='view'>TA的主页<img class='peo-icon' src="/static/images/Group 2@2x.png"></img></div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    // 增加一个可从外部传入的属性initNum
    props: {
      user: {
        type: Object
      },
      showLike: {
        type: Boolean,
        value: true
      }
    },

    data () {
      return {
        user: this.user
      }
    },

    methods: {
      onTap () {
        wx.navigateTo({
          url: '/pages/myPages/main?id=' + this.user.id
        })
      }
    }
  }
</script>

<style scoped>
  .container {
    width: 100%;
    height: 192rpx;
    padding: 30rpx 17rpx;
    display: flex;
    flex-direction: row;
  }

  .userimg {
    width: 160rpx;
    height: 160rpx;
    border-radius: 8rpx;
  }

  .description {
    display: flex;
    flex-direction: column;
    margin-left: 20rpx;
    position: relative;
    flex: 1;
  }

  .name {
    display: flex;
    align-items: center;
    line-height: 40rpx;
  }
  .nametitle {
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    line-height: 40rpx;
    font-size: 28rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(51, 62, 82, 1);
    max-width: 408rpx;
  }
  .name image {
    width: 20rpx;
    height: 21rpx;
    margin-left: 8rpx;
  }

  .moretip {
    display: flex;
    line-height: 33rpx;
    margin-top:23rpx;
  }
  .dataTips {
    display: flex;
    margin-top:35rpx;

  }
  .age {
    font-size: 24rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(131, 145, 168, 1);
  }

  .sending {
    margin-left: 50rpx;
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(131, 145, 168, 1);
  }

  .sended {
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(186, 196, 209, 1);
    line-height: 30rpx;
  }

  .geted {
    margin-left: 50rpx;
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(186, 196, 209, 1);
    line-height: 30rpx;
  }

  .view {
    font-size:22rpx;
    font-family:PingFangSC-Regular;
    font-weight:400;
    color:rgba(186, 196, 209, 1);
    line-height:35rpx;
    margin-left:40rpx;
  }

  .view image {
    width: 24rpx;
    height: 24rpx;
    vertical-align: -3rpx;
    margin-left:20rpx;
  }

</style>
