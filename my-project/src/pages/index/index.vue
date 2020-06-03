<template>
  <div class='b'>
    <image class='c' src="https://dss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=2364242578,2976026814&fm=26&gp=0.jpg" mode='widthFix'/>
    <img src="https://dss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=2364242578,2976026814&fm=26&gp=0.jpg" alt="">
    <ul>
      <li v-for="(item,index) in films" :key="index">
        <!-- <image :src="item.poster" mode='widthFix'/> -->
        <img :src="item.poster" alt="">
        <image src="https://dss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=2364242578,2976026814&fm=26&gp=0.jpg" mode='widthFix'/>
        <text>{{item.name}}</text>  
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  data () {
    return {
      films:[]
    }
  },
  props:['msg'],
  components: {

  },

  methods: {
    clickHandle()
    {

    }
  },
  mounted()
  {
    if(mpvuePlatform==='wx')
    {
      mpvue.request({
        url:'https://www.easy-mock.com/mock/5cd62f927f8f72433eeaa0b9/api/film/getList',
        success:(res)=>{
            this.films=res.data.films;
            console.log(this.films);
        }
      })
    }
  }
}
</script>

<style scoped lang='scss'>

.b{
  .c{
    width:300px;
    height: 800px;
  }
  img{
    height: 900rpx;
  }
}

</style>
