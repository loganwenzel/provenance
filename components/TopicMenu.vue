<template>
  <div class="flex overflow-x-auto p-2 bg-gray-800">
    <UButton v-for="topic in topics" :key="topic" @click="selectTopic(topic)" :class="{
      'bg-white text-black': selectedTopic === topic,
      'bg-gray-600 text-white': selectedTopic !== topic,
    }" class="mr-2 px-4 py-2 rounded-full transition duration-300">
      {{ topic }}
    </UButton>
  </div>
</template>

<script setup>
const topics = [
  'All',
  'Mechanical Engineering',
  'AI',
  'Chemistry',
  // Add more topics as needed
];

const selectedTopic = ref('All');

const selectTopic = (topic) => {
  selectedTopic.value = topic;
};
</script>

<style scoped>
/* Add any additional styles here */
</style>
