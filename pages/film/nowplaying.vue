<template>
  <div>
    <ul>
      <li v-for="data in dataList" :key="data.filmId" @click="handleClick(data.filmId)">
        <img :src="data.poster" alt="">
        <p>{{data.name}}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      dataList:[]
    }
  },
  asyncData() {
    return axios({
      url:'https://m.maizuo.com/gateway?cityId=110100&pageNum=1&pageSize=10&type=1&k=9817625',
      headers:{
        'X-Client-Info': '{"a":"3000","ch":"1002","v":"5.0.4","e":"1600074905458779816624129","bc":"110100"}',
        'X-Host': 'mall.film-ticket.film.list'
      }
    }).then(res=>{
      console.log(res.data.data);
      return{
        dataList:res.data.data.films
      }
    })
  },
  methods:{
    handleClick(id){
      this.$router.push(`/detail/${id}`)
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
