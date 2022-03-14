<template>
    <div class="tab-content" v-show="title == selectedTitle">
        <slot />
    </div>
</template>

<script>
import { inject } from 'vue'

export default {
    props: ['title'], 
    setup () {
        const selectedTitle = inject("selectedTitle")
        
        return{
            selectedTitle,
        }

    },

}
</script>

<style scoped>
.tab-content {
    min-height: 400px;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 3px 5px 5px rgba(0, 0, 0, 0.5);
    min-width: 400px;
    color: antiquewhite;
    background:#fff;
    padding:1rem;
    border-radius:0.5rem 0.5rem 0.5rem 0.5rem;
} 
</style>