<template>
  <div class="container">
    <img class='peopleimage' :src='user.userPhoto'></img>
    <div class="peopleInfoForm">
      <van-cell-group>
        <van-field v-model="user.username" clearable label="姓名" placeholder="请填写您的真实姓名"/>
        <van-cell>
          <van-radio-group class="genderItem" :value="user.gender" @change="onChangeGender">
            <van-radio name="1">先生</van-radio>
            <van-radio name="2">女士</van-radio>
          </van-radio-group>
        </van-cell>

        <van-field v-model="user.weixin" clearable label="微信号" use-slot placeholder="请填写您的微信号">
          <van-checkbox slot="button" :value="user.weixinPub" @change="onChangeWeixinPub">公开</van-checkbox>
        </van-field>
        <van-field v-model="user.phone" clearable label="手机号" use-slot placeholder="请填写您的手机号码">
          <van-checkbox slot="button" :value="user.phonePub" @change="onChangePhonePub">公开</van-checkbox>
        </van-field>
        <van-cell>
          <van-radio-group class="genderItem" :value="user.age" @change="onChangeAge">
            <van-radio name="60">60后</van-radio><van-radio name="70">70后</van-radio><van-radio name="80">80后</van-radio>
            <van-radio name="90">90后</van-radio><van-radio name="00">00后</van-radio>
          </van-radio-group>
        </van-cell>

        <van-field v-model="user.regionData" label="地区" placeholder="请选择您的所在地" readonly="readonly" @click="areaShow = true" />
        <van-popup :show="areaShow" label="地区" position="bottom" :overlay="true">
          <van-area :area-list="areaList" :value="areaCode" @cancel="onAreaCancel" @confirm="onAreaConfirm"/>
        </van-popup>
        <van-field v-model="user.jobData" label="职业" placeholder="请选择您的职业" readonly="readonly" @click="jobShow = true" />
        <van-popup :show="jobShow" label="职业" position="bottom" :overlay="true">
          <van-picker :columns="jobList" :default-index="1" @cancel="onJobCancel" @confirm="onJobConfirm"/>
        </van-popup>
      </van-cell-group>
    </div>
    <div class='sub-btn'>
      <div class='btns' @click="">保存</div>
    </div>
  </div>
</template>

<script>
  import AreaList from './area.js'
export default {
    data () {
      return {
        user: {
          userId: 123456,
          userPhoto: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
          username: '白熊',
          gender: 1,
          weixin: 'abc1234',
          weixinPub: false,
          phone: '13888888888',
          phonePub: false,
          age: 28,
          regionData: '',
          jobData: '',
          areaCode: 110101
        },
        areaShow: false,
        jobShow: false,
        areaList: AreaList,
        jobList: ['设计师', '工程师', '公务员', '自由职业']
      }
    },

    methods: {
      onAreaConfirm (e) {
        // let obj = e.mp.detail;
        // // 得到索引
        // let index = obj.index;
        // // 得到值
        // let val = obj.value;
      },
      onChangeGender (e) {
        this.user.gender = e.mp.detail
      },
      onChangeWeixinPub (e) {
        this.user.weixinPub = e.mp.detail
      },
      onChangePhonePub (e) {
        this.user.phonePub = e.mp.detail
      },
      onChangeAge (e) {
        this.user.age = e.mp.detail
      }
    }
  }
</script>

<style scoped>
  .container {
    background-color: white;
    width: 100%;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .peopleimage {
    width: 180rpx;
    height: 180rpx;
    border-radius: 50%;
    margin-top: 20rpx;
    margin: 0 auto;/*水平居中*/
  }
  .peopleInfoForm{
    display: flex;
    flex-direction: column;
    width: 100%;
    padding: 30rpx;
  }
  .genderItem{
    display: flex;
  }
  .sub-btn
  {
    bottom: 0;
    position: fixed;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #fff;
    width: 100%;
    height: 120rpx;
    box-sizing: border-box;
    padding: 16rpx 20rpx;
    z-index: 999;
  }
  .btns{
    width: 690rpx;
    height: 88rpx;
    line-height: 88rpx;
    text-align: center;
    font-family:PingFangSC-Medium;
    font-weight:500;
    color:rgba(255,255,255,1);
    line-height:48px;
    background:rgba(90,175,224,1);
    border-radius:16rpx;
  }
</style>
