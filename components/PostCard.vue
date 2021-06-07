<template>
  <div class="card">
    <NuxtLink :to="'post/' + post.slug">
      <h2 class="card__title">{{ post.title }}</h2>
    </NuxtLink>
    <small>{{ post.publicationDate }}</small>
    <p>{{ post.description || post.excerpt }}</p>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.card {
  border: 1px solid gray;
  border-radius: 5px;
  padding: 20px 2%;
  margin-top: 15px;
}

.card__title {
  font-weight: bold;
  font-size: 1.4rem;
  margin: 5px 0;
}
</style>
