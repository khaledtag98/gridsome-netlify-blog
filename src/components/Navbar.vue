<template>
  <header class="header">
    <nav class="nav">
      <ul>
        <li v-for="post in $static.posts.edges" :key="post.node.id">
          <g-link class="nav__link" :to="post.node.path">
            {{ post.node.title }}</g-link
          >
        </li>
      </ul>
    </nav>
  </header>
</template>

<static-query>
query{
 posts: allPost{
    edges{
    node{
      id
      title
      path
      }
    }
  }
}
</static-query>

<script>
export default {
  mounted() {
   
  },
};
</script>

<style scoped>
ul{
  text-decoration-style: none;
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}
</style>

 <!-- <nav class="nav">
        <g-link class="nav__link" to="/">Home</g-link>
        <g-link class="nav__link" to="/about/">About</g-link>
        <g-link class="nav__link" to="/about/">About</g-link>
      </nav> -->