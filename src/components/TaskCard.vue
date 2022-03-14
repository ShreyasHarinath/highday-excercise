<template>
    <div class="tabs">
      <ul class="tabs__header">
            <li v-for="title in tabTitles" 
            :key="title"
            :class="{ selected: title == selectedTitle }"
            @click="selectedTitle = title"  >
              {{ title }}
            </li>
      </ul>       
      <slot />
    </div>
</template>

<script>
import { ref, provide } from 'vue'
export default {
    setup (props, {slots}) {
        const tabTitles = ref(slots.default().map((tab) => tab.props.title))
        const selectedTitle = ref(tabTitles.value[0])

        provide("selectedTitle", selectedTitle)
        return {
            selectedTitle,
            tabTitles
        }
    }
}
</script>


<style scoped>
.tabs{
       max-width: 400px;
       margin: 0 auto;
       position: center;
       opacity:0.75;
       transition:100ms linear all;;
}

.tabs__header{
    margin-bottom: 10px;
    list-style: none;
    padding: 0;
    display: flex;
    text-align: center;
    text-shadow: #ddd;
    text-align-last: center;
}

.tabs__header li{
    width: 100px;
    height: 120px;
    text-align: center;
    padding: 10px 20px;
    margin-right: 10px;
    background-color: #ddd;
    border-radius: 60px;
    cursor: pointer;
    transition: 0.4s all ease-out;
}


.tabs__header li.selected {
    background-color: slateblue;
    color: whitesmoke;

}
</style>