<template>
  <div class="links">
    <nuxt-link
      v-for="post in posts"
      :to="{name: 'posts-id', params: {id: post.id}}"
      :key="post.id"
      class="button--grey"
    >
      {{post.title}}
    </nuxt-link>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Homepage',
      meta: [
          { name: 'twitter:title', content: 'Nuxt fundamentals course home page' },
          { name: 'twitter:description', content: 'The deployed environment for my Nuxt fundamentals course' }
        ]
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts.all
    }
  }
}
</script>
