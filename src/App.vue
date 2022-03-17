<template>
  <img alt="logo" src="./assets/logo-highday-600x600.png">
  <div class="placeup"><ProfilePicture></ProfilePicture></div>
  <h3>April</h3>
  <TaskCard>
    <MonthDate title="12 Wed" style="background-color: #2B3856">
      <span v-for="user of users" :key="user.id">
        <div v-for="task in user.tasks" :key="task.id">
          <div v-if="task.f === 12">
            <div class="task-container" v-bind:style="{background: user.primary_color}" >         
              <div class="title-container">
                 <h4>{{task.title}}</h4> 
              </div> 
              <div class="title-container">
                <span v-for="mem in task.members" :key="mem.members">
                  {{" | " + mem.name + " | "}}
                </span><p></p>
                <span v-for="dp in task.members" :key="dp.members"> 
                  <img class="round" alt="avatars" :src="dp.avatar" style="display:inline-block;"/> 
                </span>
              &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
              <span style="text-align: end;">
                {{task.starttime}} - {{task.endtime}} 
              </span></div>
            </div><hr>
          </div>
        </div>
      </span>
    </MonthDate>
    <MonthDate title="13 Thu" style="background-color: #2B3856">
      <span v-for="user of users" :key="user.id">
        <div v-for="task in user.tasks" :key="task.id">
          <div v-if="task.f === 13"> 
            <div class="task-container" v-bind:style="{background: user.primary_color}" >         
              <div class="title-container">
                 <h4>{{task.title}}</h4> 
              </div> 
              <div class="title-container">
                <span v-for="mem in task.members" :key="mem.members">
                  {{" | " + mem.name + " | "}}
                </span><p></p>
                <span v-for="dp in task.members" :key="dp.members"> 
                  <img class="round" alt="avatars" :src="dp.avatar" style="display:inline-block;"/> 
                </span>
              &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
              <span style="text-align: end;">
                {{task.starttime}} - {{task.endtime}} 
              </span></div>
            </div><hr>
          </div>
        </div>
      </span>
    </MonthDate>
    <MonthDate title="14 Fri" style="background-color: #2B3856">
        <span v-for="user of users" :key="user.id">
        <div v-for="task in user.tasks" :key="task.id">
          <div v-if="task.f === 14"> 
            <div class="task-container" v-bind:style="{background: user.primary_color}" >         
              <div class="title-container">
                 <h4>{{task.title}}</h4> 
              </div> 
              <div class="title-container">
                <span v-for="mem in task.members" :key="mem.members">
                  {{" | " + mem.name + " | "}}
                </span><p></p>
                <span v-for="dp in task.members" :key="dp.members"> 
                  <img class="round" alt="avatars" :src="dp.avatar" style="display:inline-block;"/> 
                </span>
              &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
              <span style="text-align: end;">
                {{task.starttime}} - {{task.endtime}} 
              </span></div>
            </div><hr>
          </div>
        </div>
      </span>
    </MonthDate>
    <MonthDate title="15 Sat" style="background-color: #2B3856">
        <span v-for="user of users" :key="user.id">
        <div v-for="task in user.tasks" :key="task.id">
          <div v-if="task.f === 15"> 
            <div class="task-container" v-bind:style="{background: user.primary_color}" >         
              <div class="title-container">
                 <h4>{{task.title}}</h4> 
              </div> 
              <div class="title-container">
                <span v-for="mem in task.members" :key="mem.members">
                  {{" | " + mem.name + " | "}}
                </span><p></p>
                <span v-for="dp in task.members" :key="dp.members"> 
                  <img class="round" alt="avatars" :src="dp.avatar" style="display:inline-block;"/> 
                </span>
              &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
              <span style="text-align: end;">
                {{task.starttime}} - {{task.endtime}} 
              </span></div>
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

.title-container{
  margin: 10px;
  text-align: start ;
  color: whitesmoke;

}

.task-container{
  margin: 0px;
  border-radius: 20px;
  color: #b3b8cd;
  text-align: center;
  width: auto;
  padding: 10px;
  max-height: auto;
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

.round{
  max-height: 40px;
  max-width: 40px;
}

.placeup {
  position: absolute;
  top: 10px;
  right: 0px;
}

hr{
  color: whitesmoke;
}

h3 
{
 text-align: center;
 line-height: 80px;
 color:blueviolet;
 font-weight: bold;
}

</style>
