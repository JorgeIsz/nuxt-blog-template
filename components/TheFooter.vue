<template>
  <footer>Made in 2021 by {{ authorName }}</footer>
</template>

<script>
import { author } from '@/lib/metadata'
export default {
  data () {
    return {
      authorName: author
    }
  }
}
</script>

<style scoped>
footer {
  height: 5vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: var(--color-alt);
}
</style>
