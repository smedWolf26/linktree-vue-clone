<script setup>
import { ref } from 'vue'
import avatar from '@/assets/SmAvatar.png'

const bio = ref({
  name: 'Saul Medina',
  avatar: avatar,
  about:
    'I am passionate about my family and my education. I have my associates degree as a network specialist and am currently working towards my Bachelor of Computer Science. I also do part time audio engineering for live bands. ',
  skills: [
    'A +',
    'Netowrk +',
    'Security +',
    'Live Sound engineering',
    'Integrated A/V systems designer',
  ],
  email: 'smedina_9827@southtexascollege.edu',
  location: 'San Juan, TX',
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:py-12">
    <RouterLink
      to="/"
      class="my-8 self-start text-sm text-gray-400 underline-offset-4 transition-colors duration-200 hover:text-blue-400 hover:underline"
    >
      ← Back to Links
    </RouterLink>

    <!--Profile Card-->
    <div
      class="w-full max-w-lg rounded-2xl border border-gray-700 bg-gray-800 p-6 shadow-xl shadow-gray-900/50 sm:p-8"
    >
      <!--Header-->
      <div
        class="mb-6 flex flex-col items-center text-center text-gray-100 sm:flex-row sm:text-left"
      >
        <div
          class="sm-mb-0 mb-4 h-20 w-20 shrink-0 overflow-hidden rounded-full border-4 border-blue-400 sm:mr-6"
        >
          <img
            :src="bio.avatar"
            :alt="bio.name"
            class="h-full w-full object-cover"
          />
        </div>
        <div>
          <h1 class="mb-1 font-display text-2xl font-bold text-white">{{ bio.name }}</h1>
          <p class="text-sm text-gray-200">📍{{ bio.location }}</p>
        </div>
      </div>
      <!--About Section-->
      <div class="mb-6">
        <H2 class="mb-3 text-lg font-semibold text-white">About</H2>
        <p class="leading-relaxed text-gray-300">{{ bio.about }}</p>
      </div>

      <!--Skills Section-->
      <div class="mb-6">
        <H2 class="mb-3 text-lg font-semibold text-white">Skills</H2>
        <div class="flex flex-wrap gap-2">
          <span
            v-for="skill in bio.skills"
            :key="skill"
            class="rounded-full bg-blue-500/50 px-3 py-1 text-sm text-blue-200"
          >
            {{ skill }}
          </span>
        </div>
      </div>

      <!--Contact-->

      <div>
        <H2 class="mb-3 text-lg font-semibold text-white">Get in Touch</H2>
        <a
          :href="`mailto:${bio.email}`"
          class="group : hover-shadow-xl inline-flex items-center gap-2 rounded-xl bg-blue-500 px-6 py-3 font-medium text-white shadow-lg shadow-blue-500/30 transition-all duration-200 hover:scale-105 hover:bg-blue-600 hover:shadow-blue-400 active:scale-95"
        >
          <svg
            data-slot="icon"
            fill="none"
            stroke-width="1.5"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
            aria-hidden="true"
            class="h-5 w-5 transition-transform duration-200 group-hover:rotate-12"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75"
            ></path>
          </svg>

          Send Email
        </a>
      </div>
    </div>
  </main>
</template>
