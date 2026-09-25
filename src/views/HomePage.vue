<script setup>
import { ref } from 'vue'
import Linkcard from '@/components/Linkcard.vue'

const Profile = ref({
  name: 'David Montoya',
  slogan: 'Full Stack Developer and Student',
  avatar:
    'https://api.dicebear.com/10.x/identicon/svg?backgroundColor=101216&rowColor=ff2e88,b400ff&rotate=-28&rowVariant=ooxoo,oxxxo,xooox,xoxox,xxoxx,xxxxx&backgroundColorFill=radial&seed=u38ur3i4',
  links:[
  {
      id: 1,
      title: 'Github',
      url: 'https://github.com/DavMont19',
      icon:'code',
      description: 'Check out my projects',
  },

  {
      id: 2,
      title: 'Linkedin',
      url:'https://www.linkedin.com/',
      icon: 'briefcase',
      description: 'Connect with me professionally',
  },
],
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8">
    <!-- Profile Header -->
    <div class="mb-8 flex flex-col items-center text-center">
      <div
        class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-green-400 shadow-lg shadow-green-500/20"
      >
        <img
          :src="Profile.avatar"
          :alt="Profile.name"
          class="h-full w-full object-cover"
        />
      </div>

      <h1
        class="mb-2 font-display text-2xl font-bold text-white sm:text-3xl"
      >
        {{ Profile.name }}
      </h1>

      <p class="max-w-xs text-gray-300 sm:text-lg">
        {{ Profile.slogan }}
      </p>
    </div>

    <!-- Link List -->
    <div class="flex w-full max-w-xs flex-col gap-4">
      <Linkcard
        v-for="link in Profile.links"
        :key="link.id"
        :title="link.title"
        :url="link.url"
        :description="link.description"
        :icon="link.icon"
      />
    </div>

    <!-- Navigate to Info -->
    <RouterLink
      to="/Info"
      class="mt-8 text-sm text-gray-400 underline-offset-4 transition-colors duration-200 hover:text-green-400 hover:underline"
    >
      About me =>
    </RouterLink>

    
  </main>
</template>
