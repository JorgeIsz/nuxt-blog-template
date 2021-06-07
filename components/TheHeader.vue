<template>
  <div class="header" :class="isIndex ? 'header--big' : 'header--small'">
    <NuxtLink to="/" class="header__title">
      <h1>{{ siteName }}</h1>
    </NuxtLink>
  </div>
</template>

<script>
import { siteName } from '@/lib/metadata'
export default {
  data () {
    return {
      siteName
    }
  },
  computed: {
    isIndex () {
      return this.$route.path === '/'
    }
  }
}
</script>
<style scoped>
.header {
  display: flex;
  align-items: center;
  background: var(--color-alt);
}

.header__title {
  font-weight: bold;
}

.header__title > h1 {
  margin: 0;
  font-size: inherit;
}

.header--small {
  height: 10vh;
  padding: 0 20px;
  font-size: 2rem;
}

.header--big {
  height: 20vh;
  justify-content: center;
  font-size: 2.8rem;
}
</style>
