<template>
  <div v-if="movieDetail">
    detail--{{$route.params.myid}}
      <img :src="movieDetail.poster" alt=""/>
      <p>{{movieDetail.name}}</p>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  layout:'detailtemplate',
  data() {
    return {
      movieDetail:null
    }
  },
  asyncData(data) {
    console.log(data.params)
    return axios({
      url:`https://m.maizuo.com/gateway?filmId=${data.params.myid}&k=9720569`,
      headers:{
        'X-Client-Info': '{"a":"3000","ch":"1002","v":"5.0.4","e":"1600074905458779816624129","bc":"110100"}',
        'X-Host': 'mall.film-ticket.film.info'
      }
    }).then(res=>{
      console.log(res.data)
      return{
        movieDetail:res.data.data.film
      }
    })
  },
}
</script>
<style scoped>

</style>
