<template>
  <div>
    center
    <ul>
      <li v-for="data in dataList" :key="data" @click=handleClick(data)>
        {{data}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dataList:["1111","2222","3333"]
    }
  },
  methods: {
    handleClick(id){
      this.$router.push(`/detail/${id}`)
    }
  },
}
</script>

<style scoped>
ul{

}
</style>
