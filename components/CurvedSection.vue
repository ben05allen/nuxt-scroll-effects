<script setup lang="ts">
const props = defineProps({
  color: String,
});
</script>

<template>
  <div class="container">
    <div class="curved">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
* {
  --curved-color: v-bind(props.color);
}
.container {
  position: relative;
}
.curved {
  background-color: var(--curved-color);
  width: 100vw;
}
.curved::before {
  content: "";
  border-top-left-radius: 75% 100%;
  border-top-right-radius: 75% 100%;
  position: absolute;
  top: -5em;
  left: 0;
  height: 5em;
  width: 100vw;
  z-index: -1;
  background-color: var(--curved-color);
}
.curved::after {
  content: "";
  border-bottom-left-radius: 75% 100%;
  border-bottom-right-radius: 75% 100%;
  position: absolute;
  bottom: -2em;
  left: 0;
  height: 2em;
  width: 100vw;
  z-index: -1;
  background-color: var(--curved-color);
}
</style>
