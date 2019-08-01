<template>
  <div class="container">
    <img class='petimg' :src="pet.image"></img>
    <div class="description">
      <div class='name'><div class='nametitle'>{{pet.name}}</div><img src="/static/images/man - anticon.png" /></div>
      <div class='moretip'>
        <div class='age'>{{pet.age}} | {{pet.newname}}</div>
      </div>
      <div class='view'> <img src="/static/images/Eye - simple-line-icons.png" />{{pet.view}}</div>
      <div class='btn-class'>
        <van-button class="btns" type="default" size="small">编辑</van-button>
        <van-button v-if="operateType == '下架'" class="btns" type="default" size="small" @click="onConfirm">下架</van-button>
        <van-button v-else class="btns" type="default" size="small" @click="onConfirm">上架</van-button>
        <van-button v-if="operateType == '下架'"  class="btns" type="default" size="small">分享</van-button>
        <van-button v-else class="btns" type="default" size="small" @click="onDelConfirm">删除</van-button>
      </div>
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
      pet: {
        type: Object
      },
      operateType: {
        type: String
      },
      showLike: {
        type: Boolean,
        value: true
      }
    },

    data () {
      return {
        pet: this.pet,
        operateType: this.operateType
      }
    },

    methods: {
      onConfirm () {
        let message = ''
        if (this.operateType === '下架') {
          message = '是否确定上架该宠物,下架后的宠物可重新上架。'
        } else {
          message = '是否确定重新上架该宠物'
        }

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

      onDelConfirm () {
        let message = '是否确定删除该宠物，删除后的宠物无法恢复。'

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
    justify-content: space-between;
    line-height: 33rpx;
    margin-top: 8rpx;
  }

  .age {
    font-size: 24rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: #8391A8;
  }

  .view {
    display: flex;
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(186, 196, 209, 1);
    margin-top: 50rpx;
  }

  .view image {
    width: 24rpx;
    height: 24rpx;
    margin-right: 8rpx;
    vertical-align: -3rpx;
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
