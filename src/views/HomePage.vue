<script setup>
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue'
import avatar from '@/assets/SmAvatar.png'

const profile = ref({
  name: 'Saul Medina',
  slogan: 'Full stack dev student',
  avatar: avatar,
  links: [
    {
      id: 1,
      title: 'Github',
      url: 'https://github.com/smedWolf26',
      icon: 'code',
      description: 'Check out my projects',
    },
    {
      id: 2,
      title: 'Linkedin',
      url: 'https://linkedin.com/in/saul-medina-a248b4161/',
      icon: 'briefcase',
      description: 'Connect with me professionally',
    },
    {
      id: 3,
      title: 'Split the Bill web app',
      url: 'https://splitthebill2026-vue.smedina-lambda.workers.dev/',
      icon: 'money',
      description: 'Need to split the bill? Click here!',
    },
  ],
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8">
    <!--Profile Header-->
    <div class="mb-8 flex flex-col items-center text-center">
      <div
        class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-blue-500 shadow-lg shadow-blue-500/20 sm:h-32 sm:w-32"
      >
        <img
          :src="profile.avatar"
          :alt="profile.name"
          class="h-full w-full object-cover"
        />
      </div>
      <h1 class="mb-2 font-display text-2xl font-bold text-white sm:text-3xl">
        {{ profile.name }}
      </h1>
      <p class="max-w-xs text-gray-300 sm:text-lg">{{ profile.slogan }}</p>
    </div>

    <!-- LInk List-->
    <div class="flex w-full max-w-md flex-col gap-4">
      <LinkCard
        v-for="link in profile.links"
        :key="link.id"
        :title="link.title"
        :url="link.url"
        :description="link.description"
        :icon="link.icon"
      />
    </div>

    <!-- Navigate to Info-->
    <RouterLink
      to="/info"
      class="mt-8 text-lg text-blue-300 underline-offset-4 transition-colors duration-200 hover:text-blue-900 hover:underline"
    >
      About me →
    </RouterLink>
  </main>
</template>
