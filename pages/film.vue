<template>
  <div>
    <ul>
      <nuxt-link to="/film/nowplaying" tag="li" activeClass="myclass1">正在热映</nuxt-link>
      <nuxt-link to="/film/comingsoon" tag="li" activeClass="myclass1">即将上映</nuxt-link>
    </ul>
    <nuxt-child></nuxt-child>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.myclass1 {
  color: orange;
}
</style>
