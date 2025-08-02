<script setup>
import { ref } from 'vue'

// Load profile pic in case you want to use it elsewhere
// const profile = ref(new URL('../assets/profilepic.png', import.meta.url).href)

// ✅ Accept props from parent
const props = defineProps({
  author: Object,
  time: String,
  content: String,
  tags: Array,
  image: String,
  likes: Array,
  comments: Array
})
</script>

<template>
  <div class="bg-white rounded-2xl shadow-md p-4 w-full max-w-2xl mx-auto mb-6 mt-5">
    <!-- Header -->
    <div class="flex items-start gap-3">
      <img :src="author.avatar" class="w-12 h-12 rounded-full object-cover" alt="Avatar" />
      <div class="flex-1">
        <div class="flex items-center space-x-1">
          <h2 class="font-semibold text-gray-900">{{ author.name }}</h2>
          <span class="text-sm text-gray-500">• {{ author.connection }}</span>
        </div>
        <p class="text-sm text-gray-500">{{ author.title }}</p>
        <p class="text-xs text-gray-400">{{ time }} ago</p>
      </div>
    </div>

    <!-- Content -->
    <div class="mt-3 text-sm text-gray-800 whitespace-pre-line">
      {{ content }}
    </div>

    <!-- Tags -->
    <div v-if="tags?.length" class="mt-2 text-blue-600 text-sm font-medium space-x-2">
      <span v-for="tag in tags" :key="tag" class="hover:underline cursor-pointer">
        #{{ tag }}
      </span>
    </div>

    <!-- Image -->
    <div v-if="image" class="mt-4">
      <img :src="image" class="w-full rounded-lg border" alt="Post Image" />
    </div>

    <!-- Reactions -->
    <div class="mt-4 flex justify-between text-sm text-gray-600">
      <div>
        👍 {{ likes.length }} • 💬 {{ comments.length }} comments
      </div>
      <div class="flex gap-4 text-sm font-medium">
        <button class="hover:text-blue-600">Like</button>
        <button class="hover:text-blue-600">Comment</button>
        <button class="hover:text-blue-600">Repost</button>
        <button class="hover:text-blue-600">Send</button>
      </div>
    </div>

    <!-- Comments -->
    <div v-if="comments?.length" class="mt-4 space-y-3">
      <div v-for="comment in comments" :key="comment.id" class="flex gap-3">
        <img :src="comment.avatar" class="w-8 h-8 rounded-full" alt="Commenter" />
        <div>
          <p class="text-sm">
            <span class="font-semibold">{{ comment.name }}</span>
            {{ comment.text }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
