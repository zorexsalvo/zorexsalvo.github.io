<template>
  <div>
    <br>
    <div class="columns">
      <div class="column">
        <figure class="image is-3by2">
            <img src="https://api.zorexsalvo.com/media/uploads/devto.jpg">
        </figure>
      </div>
      <div class="column summary">
        <p class="is-size-5 intro">
        I code in Python/Django/Flask and lately I've been doing javascript also. I'm not a
        design-guy so I'm usually assigned to do backend stuffs.<br/><br/>I'm in continuous
        loop of learning and experimenting new technologies ergo my ever-presence on many tech
        conferences, hackathons, and codecamps.<br/><br/>I do blogs too. I write about tech,
        hackathon, experiences, events, anything random that comes to mind.<br/><br/>
        </p>
      </div>
    </div>
    <hr style="margin-bottom:0">

    <section class="section">
      <div class="container">
        <h1 class="title has-text-centered has-text-left-desktop">Recent Posts</h1>
        <div class="columns is-gapless post">
          <div class="column"
               v-for="post in recentPosts"
               :key="post.id">
            <article class="tile is-child notification">
              <p class="title is-size-5 has-text-centered has-text-left-tablet">
              <router-link class="router-title"
                           :to="{ name: 'Page', params: { slug: post.slug }}">
                {{ post.title }}
              </router-link>
              </p>
              <figure class="image is-4by3">
                <img class="cover" :src="post.cover_image">
              </figure>
            </article>
          </div>

        </div>
      </div>
    </section>

  </div>
</template>

<script>
export default {
  computed: {
    recentPosts() {
      const posts = this.$store.getters.allPosts;
      return posts.splice(0, 3);
    },
  },
  created() {
    this.$store.dispatch('getPosts');
  },
};
</script>

<style scoped>
@media only screen and (min-width: 1200px) {
  .intro {
    margin-top: 1rem;
  }
}
article.tile {
  background-color: #F0F2F4;
}
p.title {
  height: 30px;
}
.router-title {
  text-decoration: none !important;
}
.cover {
  object-fit: cover;
}
article {
  padding: 1.25rem .5rem 1.25rem .5rem;
}
@media only screen and (max-width: 1000px) {
  .summary {
    margin-left: 8px;
  }
}
</style>
