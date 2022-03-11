<template>
  <TabsWrapper>
    <TabAss title="Tab 1">Hello Tab 1 </TabAss>
    <TabAss title="Tab 2">Hello t2</TabAss>
    <TabAss title="Tab 3">Hello t3</TabAss>
    <TabAss title="Tab 4">Hello Tab4</TabAss>
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
</style>
