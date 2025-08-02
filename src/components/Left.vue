<script setup>
import { ref } from 'vue'

const profile = ref(new URL('../assets/profilepic.png', import.meta.url).href)
</script>

<template>
    <div class="container">
         <div class="bg-white w-sm rounded-4xl flex flex-col p-6 gap-2">
        <img class=" rounded-full w-20 h-20" :src="profile" alt="Profile Picture"/>
        <h2 class="font-bold text-xl">Vansh Talwar</h2>
        <p>💻 Full Stack Web Developer | MEVN | Software Engineer | B.Tech... </p>
        <p>Delhi</p>
        <h4 class="font-medium text-xs" >KCC INSTITUTE OF TECHNOLOGY AND MANAGEMENT</h4>
    </div>
    
        </div>
   
</template>
