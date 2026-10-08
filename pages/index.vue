<template>
  <main>
    <Masthead />
    <AboutSection />
    <ExperienceSection />
    <FeaturedProjects />
    <section class="py-10">
      <div class="flex items-end justify-between mb-8">
        <h2>posts</h2>
        <NuxtLink to="/posts" class="text-sm font-medium text-highlight hover:underline">view all</NuxtLink>
      </div>
      <div class="grid gap-6 sm:grid-cols-2">
        <PostCard v-for="post in newestPosts" :key="post.id" :post="post" />
      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
usePageMeta(
  "Home",
  "Welcome to 8n1.net — the corner of the internet where Dan McCarthy writes, builds, and tinkers.",
);

const { data: postsData } = await useAsyncData("home-posts", () =>
  queryCollection("posts").all(),
);

const newestPosts = computed(() =>
  [...(toValue(postsData) ?? [])]
    .sort((a, b) => new Date(b.date).getTime() - new Date(a.date).getTime())
    .slice(0, 2),
);
</script>