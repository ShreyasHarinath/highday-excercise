<template>
  <img alt="logo" src="./assets/logo-highday-600x600.png">
  <div class="posii"><ProfilePicture></ProfilePicture></div>
  <h3>April</h3>
  <TaskCard>
    <MonthDate title="12 Wed" style="background-color: purple">
      <span v-for="user of users" :key="user.id">
        <div v-for="task in user.tasks" :key="task.id">
          <div v-if="task.f === 12"> 
            <div class="task-container1">              
              <div class="title-container">
                  <h4>{{task.title}}</h4></div> on {{task.date}} from 
                  {{task.starttime}}  to {{task.endtime}} with
                <span v-for="mem in task.members" :key="mem.members">
                  {{" | " + mem.name + " | "}}
                </span>
            </div><hr>
          </div>
        </div>
      </span>
    </MonthDate>
    <MonthDate title="13 Thu" style="background-color: purple">
      <span v-for="user of users" :key="user.id">
        <div v-for="task in user.tasks" :key="task.id">
          <div v-if="task.f === 13"> 
            <div class="task-container1">              
              <div class="title-container">
                  <h4>{{task.title}}</h4></div> on {{task.date}} from 
                  {{task.starttime}}  to {{task.endtime}} with
                <span v-for="mem in task.members" :key="mem.members">
                  {{" | " + mem.name + " | "}}
                </span>
            </div><hr>
          </div>
        </div>
      </span>
    </MonthDate>
    <MonthDate title="14 Fri" style="background-color: purple">
        <span v-for="user of users" :key="user.id">
        <div v-for="task in user.tasks" :key="task.id">
          <div v-if="task.f === 14"> 
            <div class="task-container1">              
              <div class="title-container">
                  <h4>{{task.title}}</h4></div> on {{task.date}} from 
                  {{task.starttime}}  to {{task.endtime}} with
                <span v-for="mem in task.members" :key="mem.members">
                  {{" | " + mem.name + " | "}}
                </span>
            </div><hr>
          </div>
        </div>
      </span>
    </MonthDate>
    <MonthDate title="15 Sat" style="background-color: purple">
        <span v-for="user of users" :key="user.id">
        <div v-for="task in user.tasks" :key="task.id">
          <div v-if="task.f === 15"> 
            <div class="task-container1">              
              <div class="title-container">
                  <h4>{{task.title}}</h4></div> on {{task.date}} from 
                  {{task.starttime}}  to {{task.endtime}} with
                <span v-for="mem in task.members" :key="mem.members">
                  {{" | " + mem.name + " | "}}
                </span>
            </div><hr>
          </div>
        </div>
      </span>
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

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50 ;
  margin-top: 60px;
  background-color: #8EEBEC;
}


h3 {
 text-align: center;
 line-height: 80px;
 color:blueviolet;
 font-weight: bold;

}


.posii {
  position: absolute;
  top: 10px;
  right: 0px;

}

.task-container{
  margin: 10px;
  background: #231e39;
  border-radius: 10px;
  color: #b3b8cd;
  width: auto;
  padding: 20px;

}

.title-container{
  margin: 10px;
  text-align: start ;
}

.task-container1{
  margin: 0px;
  background: black;
  border-radius: 20px;
  color: #b3b8cd;
  text-align: center;
  width: auto;
  padding: 40px;
}

img {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
  height: 90px;
  width: 90px;
  border-radius: 50%;
  padding: 5px;
}
</style>
