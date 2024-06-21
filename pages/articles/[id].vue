<template>
  <div class="container mx-auto py-8">
    <div class="bg-white p-8 rounded shadow">
      <img :src="article.thumbnail" alt="Article Thumbnail" class="w-full h-64 object-cover rounded">
      <h1 class="text-3xl font-bold mt-4">{{ article.title }}</h1>
      <div class="flex items-center mt-4">
        <UAvatar :src="article.reviewer.profileImage" size="sm" :title="article.reviewer.credentials" />
        <span class="ml-2">{{ article.reviewer.credentials }}</span>
      </div>
      <p class="mt-4">{{ article.content }}</p>
    </div>
  </div>
</template>

<script setup>
const route = useRoute();

const articles = [
  {
    id: 1,
    thumbnail: '/images/SampleThumbnail1.jpg',
    title: 'Understanding AI in Modern Applications',
    content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit...',
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
    content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit...',
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
    content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit...',
    reviewer: {
      id: 3,
      profileImage: '/images/SampleProfileIcon3.jpg',
      credentials: 'PhD in Chemistry',
    },
  },
];

const articleId = Number(route.params.id);
const article = articles.find(a => a.id === articleId);
</script>

<style scoped>
/* Add any additional styles here */
</style>
