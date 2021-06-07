<template>
  <div class="main-content">
    <span class="post__date">{{ post.publicationDate }}</span>
    <h1 class="post__title">
      {{ post.title }}
    </h1>
    <main>
      <NuxtContent :document="post" />
    </main>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params, redirect }) {
    try {
      const post = await $content('posts/' + params.slug).fetch()
      return {
        post
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
  color: #616161;
}

</style>
