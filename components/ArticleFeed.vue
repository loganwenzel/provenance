<template>
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 m-4">
    <NuxtLink v-for="article in articles" :key="article.id" :to="`/articles/${article.id}`"
      class="bg-white p-4 rounded shadow block no-underline hover:bg-gray-100 transition duration-300">
      <img :src="article.thumbnail" alt="Article Thumbnail" class="w-full h-48 object-cover rounded">
      <h2 class="text-xl font-bold mt-2">{{ article.title }}</h2>
      <div class="flex items-center mt-2">
        <UAvatar :src="article.reviewer.profileImage" size="sm" :title="article.reviewer.credentials" />
        <span class="ml-2">{{ article.reviewer.credentials }}</span>
      </div>
    </NuxtLink>
  </div>
</template>

<script setup>
const articles = [
  {
    id: 1,
    thumbnail: '/images/SampleThumbnail1.jpg',
    title: 'Understanding AI in Modern Applications',
    reviewer: {
      id: 1,
      profileImage: '/images/SampleProfileIcon1.jpg',
      credentials: 'PhD in Artificial Intelligence',
    },
  },
  {
    id: 2,
    thumbnail: '/images/SampleThumbnail2.jpg',
    title: 'Advances in Mechanical Engineering',
    reviewer: {
      id: 2,
      profileImage: '/images/SampleProfileIcon2.jpg',
      credentials: 'MSc in Mechanical Engineering',
    },
  },
  {
    id: 3,
    thumbnail: '/images/SampleThumbnail3.jpg',
    title: 'Recent Discoveries in Chemistry',
    reviewer: {
      id: 3,
      profileImage: '/images/SampleProfileIcon3.jpg',
      credentials: 'PhD in Chemistry',
    },
  },
];

const viewProfile = (reviewerId) => {
  // Implement profile view logic here
};
</script>

<style scoped>
/* Add any additional styles here */
</style>
