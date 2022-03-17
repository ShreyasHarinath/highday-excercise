<template>
   <div class="image-container" v-for="user in users" :key="user.id"> 
        <img class="round" alt="display_picture" :src="user.avatar">
        <div>{{user.first_name + " " + user.second_name}}</div>
    </div>

</template>

<script >

import axios from "axios";
export default {
  name: "app",
  data() {
    return{
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

.image-container {
    height:70px;
}

img {
 width: auto; 
 max-height: 100%; 
}

.round {
    border: 1px solid #03bfcb;
    border-radius: 50%;
    padding: 6px;
}

</style>

