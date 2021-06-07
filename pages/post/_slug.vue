<template>
  <div class="main-content">
    <span class="post__date">{{ post.publicationDate }}</span>
    <h1 class="post__title">
      {{ post.title }}
    </h1>
    <main>
      <NuxtContent :document="post" />
    </main>
    <div class="other-posts">
      <OtherPostLink :post="prev" side="left" />
      <OtherPostLink :post="next" side="right" />
    </div>
  </div>
</template>

<script>
import OtherPostLink from '~/components/OtherPostLink.vue'
export default {
  components: { OtherPostLink },
  async asyncData ({ $content, params, redirect }) {
    try {
      const post = await $content('posts/' + params.slug).fetch()
      const [prev, next] = await $content('posts')
        .only(['title', 'slug'])
        .sortBy('createdAt', 'asc')
        .surround(params.slug)
        .fetch()
      return {
        post,
        prev,
        next
      }
    } catch {
      redirect(404, '/404')
    }
  },
  head () {
    return {
      title: this.post.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.post.description || this.post.excerpt
        }
      ]
    }
  }
}
</script>
<style scoped>
.post__title {
  font-size: 2.5rem;
  margin-top: 10px;
  margin-bottom: 40px;
}

.post__date {
  color: var(--color-gray);
}

.other-posts {
  display: flex;
  align-items: center;
  justify-content: space-between;
  min-height: 80px;
}

</style>
