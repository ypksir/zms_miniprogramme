<template>
  <div @tap="onTap" class="container">
    <img class='petimg' :src="pet.image"></img>
    <div class="description">
      <div class='name'><div class='nametitle'>{{pet.name}}</div><img src="/static/images/man - anticon.png" /></div>
      <div class='moretip'>
        <div class='age'>{{pet.age}} | {{pet.newname}}</div>
      </div>
      <div class='tips'>{{pet.tips}}</div>
      <div class='area'>{{pet.city}}   {{pet.area}}</div>
      <div class='view'> <img src="/static/images/Eye - simple-line-icons.png" />{{pet.view}}</div>
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
      onTap () {
        wx.navigateTo({
          url: '../../pages/detail/detail?id=' + this.pet.id
        })
      }
    }
  }
</script>

<style scoped>
  .container {
    width: 100%;
    height: 256rpx;
    padding: 8rpx 0rpx;
    display: flex;
    flex-direction: row;
  }

  .petimg {
    width: 240rpx;
    height: 240rpx;
    border-radius: 8rpx;
  }

  .description {
    display: flex;
    flex-direction: column;
    margin-left: 20rpx;
    position: relative;
    flex: 1;
  }

  .age {
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(131, 145, 168, 1);
  }

  .tips {
    width: 76rpx;
    height: 38rpx;
    text-align: center;
    margin-top: 30rpx;
    line-height: 38rpx;
    background: rgba(90, 175, 224, 0.1);
    border-radius: 8rpx;
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(90, 175, 224, 1);
  }

  .name {
    display: flex;
    padding-top: 5rpx;
    margin-bottom: 3rpx;
    align-items: center;
    margin-top: 17rpx;
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
    justify-content: space-between;
    line-height: 45rpx;
  }

  .area {
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(186, 196, 209, 1);
    line-height: 70rpx;
  }

  .view {
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(186, 196, 209, 1);
    line-height: 54rpx;
    margin-right: 12rpx;
    position: absolute;
    bottom: 0rpx;
    right: 30rpx;
  }

  .view image {
    width: 24rpx;
    height: 24rpx;
    margin-right: 8rpx;
    vertical-align: -3rpx;
  }

</style>
