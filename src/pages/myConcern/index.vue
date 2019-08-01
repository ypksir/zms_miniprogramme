<template>
  <div class="container">
    <div class="user-container">
      <div v-for="(user, index) in userList" :key="index">
        <userListShow :user="user" />
      </div>
    </div>
  </div>
</template>

<script>
  import userListShow from '@/components/userListShow'
  export default {
    components: {
      userListShow
    },
    data () {
      return {
        userList: [
          {
            id: '0',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '毛球球球球球球球',
            city: '上海',
            year: '90后',
            sending: '20',
            sended: '20',
            geted: '20'
          },
          {
            id: '1',
            image: 'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
            name: '白熊…',
            city: '上海',
            year: '90后',
            sending: '20',
            sended: '20',
            geted: '28'
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
  .user-container{
    position: relative;
    width: 100%;
  }
</style>
