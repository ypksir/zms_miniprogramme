<template>
  <div class="container">
    <img class='petimg' :src="pet.image"></img>
    <div class="description">
      <div class='name'><div class='nametitle'>{{pet.name}}</div><img src="/static/images/man - anticon.png" /></div>
      <div class='moretip'>
        <div class="applyName">申请人：{{pet.applyName}}</div>
        <div class='applyAge'>{{pet.applyarea}}{{pet.applyage}}</div>
      </div>
      <div class='applyDate'>{{pet.applydate}}</div>
      <div v-if="operateType" class='btn-class'>
        <van-button class="btns" type="default" size="small" @click="onConfirm">接受</van-button>
        <van-button class="btns" type="default" size="small" @click="onRefuse">拒绝</van-button>
      </div>
      <div v-else class="cancleReason">取消原因： {{pet.cancleReason}}</div>
    </div>
    <!--
    注意要配一个van-dialog,才会显示提示 ,默认id van-dialog
    -->
    <van-dialog id="van-dialog"/>
  </div>
</template>

<script>
  // 配置文件json也要配置,这里代码也要引用
  // 代码中也要引用
  // 注意引用路径
  import Dialog from 'vant-weapp/dist/dialog/dialog'
  export default {
    // 增加一个可从外部传入的属性initNum
    props: {
      apply: {
        type: Object
      },
      operateType: {
        type: Boolean
      },
      showLike: {
        type: Boolean,
        value: true
      }
    },

    data () {
      return {
        pet: this.apply,
        operateType: this.operateType
      }
    },

    methods: {
      onConfirm () {
        let message = '是否确定接受该申请，该宠物的其他申请将自动拒绝。'
        // eslint-disable-next-line no-undef
        Dialog.confirm({
          message: message
        }).then(() => {
          // on confirm
          console.log('提交')
        }).catch(() => {
          // on cancel
          console.log('取消')
        })
      },

      onRefuse () {
        let message = '是否确定拒绝该申请，该操作无法撤销。'

        // eslint-disable-next-line no-undef
        Dialog.confirm({
          message: message
        }).then(() => {
          // on confirm
          console.log('提交')
        }).catch(() => {
          // on cancel
          console.log('取消')
        })
      }
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
  .name {
    display: flex;
    align-items: center;
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
    max-width: 408rpx;
  }

  .name image {
    width: 20rpx;
    height: 21rpx;
    margin-left: 8rpx;
  }

  .moretip {
    display: flex;
    /*justify-content: space-between;*/
    line-height: 33rpx;
    margin-top: 8rpx;
  }

  .applyName {
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    line-height: 33rpx;
    font-size: 24rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: #333E52;
    max-width: 260rpx;
  }

  .applyAge {
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    line-height: 33rpx;
    margin-left: 48rpx;
    font-size: 24rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: #8391A8;
  }

  .applyDate {
    display: flex;
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: #BAC4D1;
    margin-top: 50rpx;
  }
  .cancleReason{
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: #BAC4D1;
    position: absolute;
    bottom: 0rpx;
    margin-left: 212rpx;
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    max-width: 300rpx;
  }

  .btn-class{
    position: absolute;
    right: 0rpx;
    bottom: 0rpx;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
  }
  .btn-class .btns{
    width: 110rpx;
    height: 51rpx;
    border: 1px solid rgba(186, 196, 209, 1);
    border-radius: 8rpx;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    font-size: 24rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(51, 62, 82, 1);
    margin-right: 16rpx;
  }
</style>
