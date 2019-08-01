<template>
  <div class="container">
    <div class="animal-container">
      <div v-for="(cat, index) in catsList" :key="index">
        <catListShow :pet="cat" />
      </div>
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
            name: '毛球球球球球球球球球球球wwwwww球球…',
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

    }
  }
</script>

<style scoped>
  .container {
    background-color: white;
    width: 100%;
    position: relative;
  }
  .animal-container{
    position: relative;
    margin-top: 10rpx;
  }
</style>
