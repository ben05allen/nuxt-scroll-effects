<script setup lang="ts">
import { onMounted, ref } from "vue";

const watchedElement = ref<HTMLInputElement | null>(null);

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("animateDelay");
        }
      });
    },
    {
      threshold: 0.5,
    }
  );

  if (watchedElement.value) {
    observer.observe(watchedElement.value);
  }
});
</script>

<template>
  <div class="watchedElement" ref="watchedElement">
    <slot></slot>
  </div>
</template>

<style scoped>
.animateDelay {
  animation-duration: 5s;
  animation-fill-mode: both;
  animation-name: animateDelay;
}

@keyframes animateDelay {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }

  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
.watchedElement {
  display: inline-block;
  opacity: 0;
  transform: translateY(20px);
}
</style>
