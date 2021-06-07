<template>
  <main class="main-content">
    <PostCard v-for="post in posts" :key="post.slug" :post="post" />
  </main>
</template>

<script>
import PostCard from '~/components/PostCard.vue'
export default {
  components: { PostCard },
  async asyncData ({ $content }) {
    const posts = await $content('posts').sortBy('createdAt', 'desc').fetch()

    return {
      posts
    }
  }
}
</script>

<style scoped>
</style>
