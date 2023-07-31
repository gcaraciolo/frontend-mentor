<script setup lang="ts">
const data = [
  {
    "category": "Reaction",
    "score": 80,
    "icon": "./assets/images/icon-reaction.svg"
  },
  {
    "category": "Memory",
    "score": 92,
    "icon": "./assets/images/icon-memory.svg"
  },
  {
    "category": "Verbal",
    "score": 61,
    "icon": "./assets/images/icon-verbal.svg"
  },
  {
    "category": "Visual",
    "score": 72,
    "icon": "./assets/images/icon-visual.svg"
  }
];

const cardStyle = {
  "Reaction": {
    "bg": "bg-red-50",
    "text": "text-red-400"
  },
  "Memory": {
    "bg": "bg-yellow-50",
    "text": "text-yellow-400"
  },
  "Verbal": {
    "bg": "bg-green-50",
    "text": "text-green-400"
  },
  "Visual": {
    "bg": "bg-purple-50",
    "text": "text-purple-400"
  }
};

</script>

<template>
  <div class="bg-slate-50">
    <div class="tablet:flex items-center justify-center h-screen">
      <div class="tablet:grid grid-cols-2 max-w-xl rounded-lg drop-shadow-lg bg-white tablet:rounded-l-[2rem]">
        <header class="bg-gradient-to-b from-light-slate-blue-500 to-light-royal-blue-700 space-y-6 text-center p-5 rounded-b-[2rem] tablet:rounded-t-[2rem]">
          <span class="text-light-slate-blue-300 font-bold">Your Result</span>
          <div class="bg-gradient-to-b from-violet-blue-800 to-persian-blue-800 rounded-full w-40 h-40 mx-auto flex flex-col items-center justify-center gap-2">
            <span class="text-white text-6xl font-bold">76</span>
            <span class="text-persian-blue-400 text-xs font-bold">of 100</span>
          </div>
          <div class="space-y-4">
            <span class="text-2xl font-bold text-white">Great</span>
            <p class="text-md font-semibold text-light-royal-blue-300">You scored higher than 65% of the people who have taken these tests.</p>
          </div>
        </header>
        <main class="p-4 px-6 space-y-6 w-full">
          <h2 class="font-bold text-lg">Summary</h2>
          <ul class="space-y-4">
            <li v-for="(item, i) in data" :key="i">
              <div class="flex justify-between p-3 rounded-lg" :class="cardStyle[item.category].bg">
                <section class="flex gap-4 font-semibold" :class="cardStyle[item.category].text">
                  <img :src="item.icon" :alt="item.category" />
                  <span>{{ item.category }}</span>
                </section>
                <section class="space-x-1 text-sm">
                  <span class="font-semibold">{{ item.score }}</span>
                  <span class="text-gray-400">/ 100</span>
                </section>
              </div>
            </li>
          </ul>
          <button type="button" class="bg-gray-700 text-gray-300 font-semibold rounded-full w-full p-4 tablet:p-2 hover:bg-gradient-to-b hover:from-light-slate-blue-500 hover:to-light-royal-blue-700 hover:text-light-royal-blue-100">Continue</button>
        </main>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
</style>
