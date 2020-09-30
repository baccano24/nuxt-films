<template>
  <div>
    <nuxt />
    <ul class="tabbar">
      <nuxt-link to="/film" tag="li" activeClass="myclass">film</nuxt-link>
      <nuxt-link to="/center" tag="li" activeClass="myclass">center</nuxt-link>
      <nuxt-link to="/cinema" tag="li" activeClass="myclass">cinema</nuxt-link>
    </ul>
  </div>
</template>

<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
.tabbar {
  list-style: none;
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 50px;
  background: white;
  display: flex;
  z-index: 9999;
}
.tabbar li {
  background: skyblue;
  flex: 1;
  line-height: 50px;
  text-align: center;
  font-size: 18px;
}
.myclass {
  color: red;
}
</style>
