<template>
  <div>
    <ul>
      <li v-for="data in movieList" :key="data.id">
        {{data.nm}}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      movieList:[]
    }
  },
  asyncData() {
    console.log(process.server)
    return axios({
      url: process.server?"https://m.maoyan.com/ajax/movieOnInfoList?token=":"/ajax/movieOnInfoList?token=",
    }).then((res) => {
      console.log(res.data);
      return {
        movieList: res.data.movieList
      };
    });
  },
};
</script>

<style scoped>
</style>
