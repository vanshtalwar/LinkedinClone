<script setup>
import { ref } from 'vue'

const profile = ref(new URL('../assets/profilepic.png', import.meta.url).href)
</script>

<template>
    <div class="container bg-white p-5 w-full rounded-4xl mb-5">


        <div class="flex gap-5 items-center">
            <img class=" rounded-full w-15 h-15" :src="profile" alt="">
            <input class="border rounded-full w-lg p-3 h-10" type="text" placeholder="Start a post">

        </div>

        <div class="flex justify-between">
            <h4>🎥 Video</h4>
            <h4>📸 Photo</h4>
            <h4>📝 Write Article</h4>
        </div>
    </div>
</template>