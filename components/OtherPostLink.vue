<template>
  <NuxtLink v-if="post" :to="post.slug" class="container">
    <span v-if="side === 'left'">&#8592;</span>
    <span class="main-text">{{ post.title }}</span>
    <span v-if="side === 'right'">&#8594;</span>
  </NuxtLink>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true
    },
    side: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.container {
  border: 1px solid #cecece;
  border-radius: 5px;
  width: clamp(200px, 50%, 350px);
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: var(--color-primary);
}

.main-text {
  font-size: 18px;
  margin: 0 8px;
}
</style>
