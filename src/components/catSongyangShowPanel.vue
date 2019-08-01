<template>
  <div class="container">
    <img class='petimg' :src="pet.image"></img>
    <div class="description">
      <div class="basicTip">
        <div class='name'><div class='nametitle'>{{pet.name}}</div><img src="/static/images/man - anticon.png" /></div>
        <div class="lingyangName"><span class='lingyangNametitle'>领养人：{{pet.lingyangName}}</span></div>
      </div>
      <div class='moretip'>
        <div class='phone'><img src="/static/images/detail/smartphone - material.png" /><div class='phonetitle'>{{pet.phone}}</div></div>
        <div class='weixin'><img src="/static/images/detail/weixin.png" /><div class='weixintitle'>{{pet.weixin}}</div></div>
      </div>
      <div class='date'>{{pet.date}}</div>
    </div>
  </div>
</template>

<script>
  export default {
    // 增加一个可从外部传入的属性initNum
    props: {
      pet: {
        type: Object
      },
      showLike: {
        type: Boolean,
        value: true
      }
    },

    data () {
      return {
        pet: this.pet
      }
    },

    methods: {

    }
  }
</script>

<style scoped>
  .container {
    width: 100%;
    height: 192rpx;
    display: flex;
    flex-direction: row;
  }

  .petimg {
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

  .basicTip{
    display: flex;
  }
  .name {
    display: flex;
    align-items: center;
    width: 250rpx;
  }
  .nametitle {
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    line-height: 40rpx;
    font-size: 28rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: #333E52;
    max-width: 208rpx;
  }
  .name img {
    width: 20rpx;
    height: 21rpx;
    margin-left: 8rpx;
  }
  .basicTip .lingyangName{
    margin-left: 50rpx;
  }
  .basicTip .lingyangName .lingyangNametitle{
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    line-height: 33rpx;
    font-size: 24rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: #333E52;
    max-width: 200rpx;
  }
  .moretip{
    display: flex;

  }
  .moretip .phone{
     display: flex;
     margin: 16rpx 0rpx;
     align-items: center;
     width: 250rpx;
   }
  .moretip .phone .phonetitle {
    margin-left: 8rpx;
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    line-height: 37rpx;
    font-size: 26rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: #8391A8;
    max-width: 200rpx;
  }
  .moretip .phone img {
    width: 20rpx;
    height: 20rpx;
  }
  .moretip .weixin{
    display: flex;
    margin-left: 50rpx;
    align-items: center;

  }
  .moretip .weixin .weixintitle {
    margin-left: 8rpx;
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    line-height: 37rpx;
    font-size: 26rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: #8391A8;
    max-width: 150rpx;
  }
  .moretip .weixin img {
    width: 20rpx;
    height: 20rpx;
  }
  .date{
    margin-top: 22rpx;
    line-height: 30rpx;
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: #BAC4D1;
  }

</style>
