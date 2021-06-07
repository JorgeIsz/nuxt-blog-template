<template>
  <div class="content">
    <h1>Oops. Looks like that page doesn't exist anymore</h1>
    <NuxtLink class="link-to-home" to="/">
      Go back to home
    </NuxtLink>
  </div>
</template>

<style scoped>
.content {
  height: 50vh;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
.link-to-home {
  border-bottom: 2px solid var(--color-gray);
}

</style>
