<template>
  <nav class="nav">
    <g-link class="nav__link" to="/">Home</g-link>
    <g-link class="nav__link" to="/about/">About</g-link>
    <g-link v-for="post in $static.posts.edges" :key="post.id" class="nav__link" :to="post.node.path">
      {{ post.node.title }}
    </g-link>
  </nav>
</template>

<script>
export default {
  name: "MainNav"
}
</script>

<static-query>
query Posts {
  posts: allPost {
    edges {
      node {
        id
        title
        path
      }
    }
  }
}
</static-query>

<style>
.nav__link {
  margin-left: 20px;
}
</style>