<template>
  <div class="container">
    <div class='title'>
      <van-tabs swipeable animated :active="active" @change="onChange">
        <van-tab title="待送养">
          <div class="animal-container">
            <div v-for="(cat, index) in catsList" :key="index">
              <catSongyangEditPanel :pet="cat" :operateType="下架"/>
            </div>
          </div>
        </van-tab>
        <van-tab title="已送养">
          <div class="animal-container">
            <div v-for="(cat, index) in catsList2" :key="index">
              <catSongyangShowPanel :pet="cat" />
            </div>
          </div>
        </van-tab>
        <van-tab title="已下架">
          <div class="animal-container">
            <div v-for="(cat, index) in catsList" :key="index">
              <catSongyangEditPanel :pet="cat" :operateType="上架"/>
            </div>
          </div>
        </van-tab>
      </van-tabs>
    </div>
  </div>
</template>

<script>
  import catSongyangEditPanel from '@/components/catSongyangEditPanel'
  import catSongyangShowPanel from '@/components/catSongyangShowPanel'
  export default {
    components: {
      catSongyangEditPanel,
      catSongyangShowPanel
    },

    data () {
      return {
        catsList: [
          {
            id: '0',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '毛球球球球球球球',
            lingyangName: '小娃',
            phone: 13888888888,
            weixin: 'asffsgf',
            date: '2019.03.02'
          },
          {
            id: '1',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '毛球球球球球球球球球球球wwwwww球球…',
            lingyangName: '小娃',
            phone: 13888888888,
            weixin: 'asffsgf',
            date: '2019.03.02'
          }
        ],

        catsList2: [
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
        ]
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
  .title {
    height: 80rpx;
  }
  .animal-container{
    padding: 16rpx 30rpx;
  }
</style>
