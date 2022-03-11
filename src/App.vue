<template>

  <img alt="logo" src="./assets/logo-highday-600x600.png">
  <h3>April</h3>
  <TabsWrapper>
    <TabAss title="12">Hello Tab 1 </TabAss>
    <TabAss title="13">Hello t2</TabAss>
    <TabAss title="14">Hello t3</TabAss>
    <TabAss title="15">Hello Tab4</TabAss>
  </TabsWrapper>
</template>

<script setup>
import TabAss from './components/TabAss.vue'
import TabsWrapper from './components/TabsWrapper.vue'
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

img {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
  height: 50px;
  width: 50px;
  border-radius: 100%;
}
h3 {
 text-align: center;
 line-height: 100px;
 color:blueviolet;

}
body {
  background-color: lightblue;
}
</style>
