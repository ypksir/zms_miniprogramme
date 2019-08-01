<template>
  <div class="container">
    <div class='title'>
      <van-tabs swipeable animated :active="active" @change="onChange">
        <van-tab title="待审核"></van-tab>
        <van-tab title="确认送养"></van-tab>
        <van-tab title="已取消"></van-tab>
      </van-tabs>
    </div>
    <div class="receiveApplyList">
      <div v-if="index == 0" class="animal-container">
        <div v-for="(apply, index) in applyIngList" :key="index">
          <applyEditPanel :apply="apply":operateType=applyIng />
        </div>
      </div>

      <div v-if="index == 1" class="animal-container">
        <div v-for="(cat, index) in applyedList" :key="index">
          <catSongyangShowPanel :pet="cat" />
        </div>
      </div>

      <div v-if="index == 2" class="animal-container">
        <div v-for="(apply, index) in applyIngList" :key="index">
          <applyEditPanel :apply="apply" :operateType=cancleApply />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import applyEditPanel from '@/components/applyEditPanel'
  import catSongyangShowPanel from '@/components/catSongyangShowPanel'
  export default {
    components: {
      applyEditPanel,
      catSongyangShowPanel
    },

    data () {
      return {
        index: 0,
        active: 0,
        applyIngList: [
          {
            id: '0',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '栗子',
            applyName: '海华',
            applyarea: '上海',
            applyage: '90后',
            applydate: '2019.07.02',
            cancleReason: '该宠物已下架'
          },
          {
            id: '1',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '栗子',
            applyName: '格式',
            applyarea: '上海',
            applyage: '90后',
            applydate: '2019.07.02',
            cancleReason: '该宠物已确认送养'
          },
          {
            id: '1',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '栗子…',
            applyName: '设个人',
            applyarea: '上海',
            applyage: '90后',
            applydate: '2019.07.02',
            cancleReason: '该宠物已确认送养'
          },
          {
            id: '1',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '栗子…',
            applyName: '推介会让',
            applyarea: '上海',
            applyage: '90后',
            applydate: '2019.07.02',
            cancleReason: '已拒绝该申请'
          }
        ],

        applyedList: [
          {
            id: '0',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '栗子',
            lingyangName: '小娃',
            phone: 13888888888,
            weixin: 'asffsgf',
            date: '2019.03.02'
          },
          {
            id: '1',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '花化',
            lingyangName: '小娃',
            phone: 13888888888,
            weixin: 'asffsgf',
            date: '2019.03.02'
          },
          {
            id: '1',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '小狸狸狸狸狸狸狸狸狸狸狸狸狸',
            lingyangName: '小娃',
            phone: 13888888888,
            weixin: 'asffsgf',
            date: '2019.03.02'
          }
        ],
        applyIng: true,
        cancleApply: false
      }
    },

    methods: {
      onChange (event) {
        this.index = event.mp.detail.index
        this.active = event.mp.detail.index
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
  .title {
    height: 80rpx;
    width: 100%;
  }
  .receiveApplyList {
    position: relative;
    width:100%;
  }
  .animal-container{
    padding: 16rpx 30rpx;
    position: relative;
  }
</style>
