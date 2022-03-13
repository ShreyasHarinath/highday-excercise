<template>

  <img alt="logo" src="./assets/logo-highday-600x600.png">
  <div class="posii"><ProfilePicture></ProfilePicture></div>
  <h3>April</h3>
  <TaskCard>
    <MonthDate title="12" style="background-color: purple">
      <div class="task-container">
        <div class="title-container">
          <span v-for="user of users" :key="user.id">
            <ul><li v-for="task in user.tasks" :key="task.id">{{task.title}}{{task.starttime}} to {{task.endtime}}</li></ul></span></div></div>
    </MonthDate>
    <MonthDate title="13" style="background-color: purple">
      <div class="task-container">
        <div class="title-container">
          <li v-for="user of users" :key="user.id">{{user.email}}</li></div></div>
    </MonthDate>
    <MonthDate title="14" style="background-color: purple">
        <div class="task-container">
         <div class="title-container">
           <li v-for="user of users" :key="user.id">{{user.username}}</li></div></div>
    </MonthDate>
    <MonthDate title="15" style="background-color: purple">
        <div class="task-container">
        <div class="title-container">
          <li v-for="user of users" :key="user.id">{{user.tasks}}</li></div></div>
    </MonthDate>
  </TaskCard>

</template>

<script>
import axios from "axios";
import MonthDate from './components/MonthDate.vue';
import TaskCard from './components/TaskCard.vue';
import ProfilePicture from './components/ProfilePicture.vue';


export default {
  components: { TaskCard, MonthDate, ProfilePicture },
  name: "app",
  data() {
    return {
     users : []
    }
  },
  async created() {
    try {
      const res = await axios.get('http://localhost:3000/users');

      this.users = res.data;
    } catch (e) {
        console.error(e);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50 ;
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
.posii {
  position: absolute;
  top: 0px;
  right: 0px;

}
.task-container{
  margin: 50px;
  background: #231e39;
  border-radius: 10px;
  color: #b3b8cd;
  text-align: center;
  width: auto;
  padding: 20px;

}
.title-container{
  margin: 10px;
}
</style>
