<template>
  <div>
    <section class="mx-20 top">
      <h1 class="text-4xl text-red-400 my-40">This is a heading</h1>
      <div class="px-20 my-40 bg-blue-400 py-72 w-full">a big blue box</div>
    </section>

    <CurvedSection color="aliceblue">
      <div class="px-40">
        <h2 class="text-2xl text-green-300">the next section</h2>
        <ScrollDelay>
          <div class="my-40 bg-pink-300 py-24 text-center w-40">
            a smaller red box
          </div>
        </ScrollDelay>
      </div>
    </CurvedSection>

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
</style>
