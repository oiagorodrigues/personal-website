<template>
  <section id="post__list" class="post__list">
    <div v-for="post in $page.posts.edges" class="card" :key="post.node.id">
      <article class="post-item">
        <h1 class="post-title">{{post.node.title}}</h1>
        <p class="post-description" v-html="post.node.excerpt"></p>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  name: "PostsList",
  metaInfo: {
    title: "Blog"
  },
  mounted() {
    console.log(this.$page.posts);
  }
};
</script>

<page-query>
query Posts {
    posts: allPost {
      edges {
        node {
          id
          title
          path
          excerpt
          date (format: "DD/MM/YYYY")
          timeToRead
          ...on Post {
            id
            title
            path
          }
        }
      }
    }
}
</page-query>

<style lang="scss" scoped>
.card {
  border: 1px solid #fafafa;
  box-shadow: 0 0 12px #dedede;
  padding: 0.5rem 2rem;
  margin-bottom: 2rem;
  cursor: pointer;
  transition: box-shadow 0.4s ease-in;
  &:hover {
    box-shadow: 0 0 28px 12px #dedede;
  }
}
</style>