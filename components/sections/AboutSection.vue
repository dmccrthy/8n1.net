<template>
  <section class="flex flex-col md:flex-row items-center pb-10 md:h-96">
    <div class="pb-8 md:pb-0 md:w-1/2">
      <h2>about me</h2>
      <p>
        Hi, my name's Dan and I'm a
        <i>Software Developer</i> from <i>New Hampshire</i> with interests in computer networking
        and cybersecurity. I'm currently working towards a BS in Information Technology at the
        University of New Hampshire. If you want to get in touch, my links are below.
      </p>
    </div>
    <figure class="group relative mx-auto rotate-2">
      <div
        aria-hidden="true"
        class="absolute inset-0 translate-x-3 translate-y-3 bg-alt shadow-lg transition-transform duration-300 group-hover:translate-x-5 group-hover:translate-y-5"
      />
      <div class="relative transition-transform duration-300 group-hover:-translate-y-2">
        <NuxtImg
          src="/images/headshot.jpg"
          width="400"
          alt="Picture of Dan McCarthy"
          class="w-60 h-72 object-cover shadow-2xl"
        />
        <div
          aria-hidden="true"
          class="absolute -top-3 left-1/2 -translate-x-1/2 -rotate-3 w-32 h-6 bg-white/60 backdrop-blur-[1px] shadow-sm"
        />
      </div>
    </figure>
  </section>
</template>
