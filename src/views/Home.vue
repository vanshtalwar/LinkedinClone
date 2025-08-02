<script setup>
import Navbar from '@/components/Navbar.vue';
import Left from '@/components/Left.vue'
import Mid from '@/components/Mid.vue';
import Right from '@/components/RIght.vue';
import Post from '@/components/Post.vue';
import { ref } from 'vue'
const getImageUrl = (path) => {
    return new URL(`../assets/${path}`, import.meta.url).href;
};
const posts = ref([
    {
        author: {
            name: 'Vansh Talwar',
            connection: '2nd',
            title: 'Student at Raj Kumar Goel Institute of Technology, Ghaziabad',
            avatar: getImageUrl('profilepic.png'),
        },
        time: '1w',
        content: `Achieved LeetCode 200-day badge. Honed skills in algorithmic paradigms, 
complexity analysis, and optimized data structure implementation.`,
        tags: ['LeetCode', 'Algorithms', 'DataStructures', 'ProblemSolving', 'SoftwareEngineering'],
        image: './src/assets/post.jpeg',
        likes: ['Aditya Singh', 'User2', 'User3'],
        comments: [
            {
                id: 1,
                name: 'Aditya Singh',
                avatar: 'https://placehold.co/80x80',
                text: 'Congratulations!'
            }
        ]
    },
    {
        author: {
            name: 'Shivansh Talwar',
            connection: '2nd',
            title: 'Student at Raj Kumar Goel Institute of Technology, Ghaziabad',
            avatar: '',
        },
        time: '1w',
        content: `Achieved LeetCode 200-day badge. Honed skills in algorithmic paradigms, 
complexity analysis, and optimized data structure implementation.`,
        tags: ['LeetCode', 'Algorithms', 'DataStructures', 'ProblemSolving', 'SoftwareEngineering'],
        image: './src/assets/post.jpeg',
        likes: ['Aditya Singh', 'User2', 'User3'],
        comments: [
            {
                id: 1,
                name: 'Aditya Singh',
                avatar: 'https://placehold.co/80x80',
                text: 'Congratulations!'
            }
        ]
    }
])
</script>

<template>
    <div>
        <Navbar />
    </div>


    <div class="flex gap-10 mt-10 px-10">
        <aside>
            <Left />
        </aside>

        <main>
            <Mid />
            <hr>
            <Post v-bind="post" v-for="post in posts" :key="post.image" />
        </main>

        <aside>
            <Right />
        </aside>

    </div>

</template>