<script setup>
import logo from "@/assets/logo.png"
</script>

<template>
    <div class="container flex lg:w-full justify-around bg-white">

        <div id="nav1" class="flex items-center m-2" >
            <img class="h-10" :src="logo" alt="">
            <input class="border rounded-2xl px-2 h-10" type="text" placeholder="Search">
        </div>

        <div id="nav2" class="flex items-center gap-5">
            <p>Home</p>
            <p>My Networks</p>
            <p>Jobs</p>
            <p>Messaging</p>
            <p>Notifications</p>
            <p>Me</p>
            <p class="border-l-2 p-3">For Business</p>
            <p>Try Premiuim for ₹0</p>

        </div>


    </div>
</template>

<style scoped>
#nav2 p{
    margin: 5px;
}
</style>