<template>
  <div class="container">
    <div class='personalPage'>
      <div class='personalInfo'>
        <img class='peopleimage' :src='user.userPhoto'></img>
        <div class='peopleinfo'>
          <span class='peoplename'>{{user.userName}}
            <img class='peo-icon' src="/static/images/woman - anticon.png"></img>
          </span>
          <span class='peopleid'>ID: {{user.userId}}</span>
        </div>
        <span class='peoplePage' @click="concernPeople">
          <van-tag v-if="user.isActive" size="large">已关注</van-tag>
          <van-tag v-else type="primary" size="large">关注</van-tag>
       </span>
      </div>
      <div class="headline">TA的送养</div>
      <div class="animal-container">
        <div v-for="(cat, index) in catsList" :key="index">
          <catListShow :pet="cat" />
        </div>
      </div>
    </div>
    <div class='sub-btns'>
      <div class='btn-z'> <img class='btn-icon' src="/static/images/detail/export - anticon.png"></img></div>
    </div>
  </div>
</template>

<script>
  import catListShow from '@/components/catListShow'
  export default {
    components: {
      catListShow
    },
    data () {
      return {
        user: {
          userId: 123456,
          userPhoto: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
          userName: '白熊',
          isActive: false
        },
        catsList: [
          {
            id: '0',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '毛球球球球球球球',
            age: '1岁1个月',
            newname: '狸花',
            tips: '亲人',
            city: '上海',
            area: '普陀',
            view: '20'
          },
          {
            id: '1',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '毛球球球球球球球球球球球wwwwww球',
            age: '1岁1个月',
            newname: '狸花',
            tips: '亲人',
            city: '上海',
            area: '普陀',
            view: '20'
          }
        ]
      }
    },

    methods: {
      concernPeople () {
        if (this.user.isActive) {
          this.user.isActive = false
        } else {
          this.user.isActive = true
        }
      }
    }
  }
</script>

<style scoped>
  .container {
    background-color: white;
    width: 100%;
    position: relative;
  }
  .personalInfo {
     height:180rpx;
     background:rgba(255, 255, 255, 1);
     border-bottom:2rpx solid #E6EAEF;
     border-radius:16rpx;
     display:flex;
     position:relative;
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
    font-size: 22rpx;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(186, 196, 209, 1);
    top: 32rpx;
    right: 30rpx;
  }
  .headline {
    font-size: 34rpx;
    font-weight: 500;
    color: #2f2f2f;
    margin-top: 60rpx;
    margin-bottom: 20rpx;
  }
  .animal-container{
    position: relative;
    margin-top: 10rpx;
  }
  .sub-btns
  {
    bottom: 120rpx;
    position: fixed;
    display: flex;
    flex-direction: row;
    background-color: transparent;
    box-sizing: border-box;
    z-index: 999;right: 30rpx;height: 160rpx;
  }
  .btn-z{
    width:96rpx;
    height:96rpx;
    background:rgba(193,232,230,1);
    box-shadow:0px 28rpx 56rpx 0px rgba(79,99,130,0.06),0px 16rpx 32rpx 0px rgba(79,99,130,0.03);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .btn-icon{
    width: 33rpx;
    height: 33rpx;
  }
</style>
