<template>
  <div class="mx-20">
    <h1 class="text-4xl text-red-400 my-40">
      This is a heading
    </h1>
    <ScrollEffect1 />
    <div class="my-40 bg-blue-400 py-72 w-full">
      a big blue box
    </div>
    <div ref="demo" class="my-40 bg-pink-300 py-60 w-40 demo">
      a smaller red box
    </div>
  </div>
</template>

<script setup>

import { onMounted, ref } from 'vue';

const demo = ref('');

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          // add 'animate-delay' class to the target
          entry.target.classList.add('animate-delay');
        }
      });
    },
    {
      threshold: 0.5,
    }
  );

  // observe each element
  if (demo.value) {
    observer.observe(demo.value);
  }
});

</script>

<style scoped>
.animate-delay {
  animation-duration: 5s;
  animation-fill-mode: both;
  animation-name: animate-delay;
}

@keyframes animate-delay {
  0% {
    opacity: 0;
    transform: translateY(20px);
    -webkit-transform: translateY(40px);
    -moz-transform: translateY(20px);
    -ms-transform: translateY(20px);
    -o-transform: translateY(20px);
  }

  100% {
    opacity: 1;
    transform: translateY(0);
    -webkit-transform: translateY(0);
    -moz-transform: translateY(0);
    -ms-transform: translateY(0);
    -o-transform: translateY(0);
  }
}

.demo {
  display: inline-block;
  opacity: 0;
  transform: translateY(20px);
  -webkit-transform: translateY(20px);
  -moz-transform: translateY(20px);
  -ms-transform: translateY(20px);
  -o-transform: translateY(20px);
}
</style>