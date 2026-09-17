<script setup>
import {ref} from 'vue'
import Linkcard from '@/components/Linkcard.vue';

const Profile = ref({
  name: 'David Montoya',
  slogan: 'Full Stack Developer and Student',
  avatar:
  'https://api.dicebear.com/10.x/identicon/svg?backgroundColor=101216&rowColor=ff2e88,b400ff&rotate=-28&rowVariant=ooxoo,oxxxo,xooox,xoxox,xxoxx,xxxxx&backgroundColorFill=radial&seed=u38ur3i4'

})

</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8">
    <!-- Profile Header -->
     <div class = "mb-8 flex flex-col items-center text-center">
      <div class = "mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-green-400 shadow-lg shadow-green-500/20">
      <img 
      :src="Profile.avatar" 
      :alt="Profile.name"
      class = "h-full w-full object-cover"
      />
     </div> 
      <h1 class ="font-display mb-2 text-2xl font-bold text-white sm:text-3xl">{{Profile.name}}</h1>
      <p class="max-w-xs text-gray-300 sm:text-lg"> {{Profile.slogan}} </p>
     </div>
  </main>
</template>
