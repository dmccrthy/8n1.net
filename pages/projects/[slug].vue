<template>
  <main class="px-6 md:px-16 py-10 space-y-6">
    <NuxtLink to="/projects" class="inline-block mb-6 text-sm font-medium text-highlight hover:underline">
      ← Back to projects
    </NuxtLink>

    <article v-if="project" class="prose prose-main max-w-none">
      <header class="mb-8">
        <p class="text-sm font-semibold text-highlight mb-2">
          {{
            new Date(project.date).toLocaleDateString("en-US", {
              month: "short",
              day: "numeric",
              year: "numeric",
            })
          }}
        </p>
        <h1 class="text-4xl font-bold mb-4">{{ project.title }}</h1>
        <p class="text-lg text-font-muted">{{ project.description }}</p>
        <div class="flex flex-wrap gap-2 mt-4">
          <span
            v-for="tag in project.tags"
            :key="tag"
            class="px-3 py-1 rounded-full text-sm font-medium border border-alt"
          >
            {{ tag }}
          </span>
        </div>
      </header>

      <NuxtImg
        v-if="project.image"
        :src="project.image"
        :alt="project.title"
        class="w-full h-auto max-h-[500px] object-cover rounded-lg my-8"
      />

      <div class="prose prose-main max-w-none">
        <ContentRenderer :value="project" />
      </div>

      <div v-if="project.link" class="mt-8 pt-8 border-t border-alt">
        <a
          :href="project.link"
          target="_blank"
          rel="noopener noreferrer"
          class="inline-flex items-center gap-2 px-6 py-3 rounded-lg bg-highlight text-white font-medium hover:opacity-90 transition-opacity"
        >
          <Icon name="lucide:external-link" mode="svg" class="size-4" />
          View Project
        </a>
      </div>
    </article>

    <p v-else class="text-center text-font-muted py-12">Project not found.</p>
  </main>
</template>

<script setup lang="ts">
const route = useRoute();
const slug = route.params.slug;

const { data: project } = await useAsyncData(`project-${slug}`, () =>
  queryCollection("projects").where("_id", "==", slug).first(),
);

usePageMeta(
  project.value?.title ?? "Project Not Found",
  project.value?.description ?? "",
);
</script>