<template>
  <div>
    <section class="mx-20 top">
      <h1 class="text-4xl text-red-400 my-40">This is a heading</h1>
      <div class="my-40 bg-blue-400 py-72 w-full">a big blue box</div>
    </section>
    <section class="px-20 bubble">
      <h2 class="text-2xl text-green-300">the next section</h2>
      <ScrollEffect1>
        <div class="my-40 bg-pink-300 py-24 text-center w-40">
          a smaller red box
        </div>
      </ScrollEffect1>
    </section>

    <section class="lastSection">This is the last section</section>
  </div>
</template>

<style scoped>
section {
  position: relative;
}
.lastSection {
  margin: 10rem 10rem;
}
.lastSection::before {
  content: "👌🏻 ";
}
.lastSection::after {
  content: " 😀";
}
.bubble {
  background-color: aliceblue;
}
.bubble::before {
  content: "";
  border-top-left-radius: 75% 100%;
  border-top-right-radius: 75% 100%;
  position: absolute;
  top: -5em;
  left: 0;
  height: 5em;
  width: 100%;
  z-index: -1;
  background-color: aliceblue;
}
.bubble::after {
  content: "";
  border-bottom-left-radius: 75% 100%;
  border-bottom-right-radius: 75% 100%;
  position: absolute;
  bottom: -2em;
  left: 0;
  height: 2em;
  width: 100%;
  z-index: 1;
  background-color: aliceblue;
}
</style>
