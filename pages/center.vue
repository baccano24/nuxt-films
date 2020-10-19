<template>
  <div>
    搜索：<input type="text" v-model="search" @input="searchList(search)" />
    <ul>
      <li v-for="data in movieList" :key="data.id">
        <p>{{data.nm}}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      search: "",
      movieList: [],
    };
  },
  methods: {
    searchList(data) {
      // console.log(this.search);
      this.search = data;
      axios(`/ajax/search?kw=${this.search}&cityId=1&stype=-1`).then((res) => {
        // console.log(res.data.movies);
        this.movieList = res.data.movies.list;
      }).catch(err=>{
        console.log(err)
      })
    },
  },
};
</script>

<style scoped>

</style>
