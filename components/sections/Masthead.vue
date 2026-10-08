<template>
  <section class="py-16 md:py-24 text-center">
    <h1 class="text-4xl md:text-6xl font-bold mb-6 leading-tight">
      Hi, I'm <span class="text-highlight">Dan McCarthy</span>
    </h1>
    <p class="text-lg md:text-xl text-font-muted max-w-2xl mx-auto mb-10 leading-relaxed">
      Software Developer from New Hampshire with interests in computer networking and cybersecurity.
    </p>
    <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
      <NuxtLink
        to="/projects"
        class="px-6 py-3 rounded-lg font-medium transition-colors bg-highlight text-main hover:bg-highlight/80 text-center no-underline"
      >
        View Projects
      </NuxtLink>
      <NuxtLink
        to="/posts"
        class="px-6 py-3 rounded-lg font-medium transition-colors border-2 border-alt text-font hover:border-highlight/50 hover:text-highlight bg-main text-center no-underline"
      >
        Read Posts
      </NuxtLink>
    </div>
  </section>
</template>
