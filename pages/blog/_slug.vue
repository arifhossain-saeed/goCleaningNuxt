<template>
  <section>
    <TheBlogDetailBanner />
    <div class="clearfix"></div>
    <TheBlogDetailBody2 :posts="posts" :article="article" />
<!--    <nuxt-content :document="article" />-->
    <div class="clearfix"></div>
  </section>
</template>

<script>
import TheBlogDetailBanner from "@/components/blog/TheBlogDetailBanner";
import TheBlogDetailBody2 from "@/components/blog/TheBlogDetailBody2";
export default {
  head () {
    return {
      title: this.article.title,
      meta: [
        { hid: 'description', name: 'description', content: this.article.description },
        { hid: 'og:title', property: 'og:title', content: this.article.title },
        { hid: 'og:description', property: 'og:description', content: this.article.description },
        { hid: 'twitter:title', name: 'twitter:title', content: this.article.title },
        { hid: 'twitter:description', name: 'twitter:description', content: this.article.description }
      ]
    }
  },

  components: {
    TheBlogDetailBanner, TheBlogDetailBody2
  },

  async asyncData({ $content, params }) {
    // console.log(params)
    const posts = await $content('posts').sortBy('createdAt', 'desc').fetch()
    const article = await $content('posts', params.slug).fetch()
    return { posts, article }
  },
}
</script>

<style>
.nuxt-content h2 {
  font-weight: bold;
  font-size: 28px;
}
.nuxt-content h3 {
  font-weight: bold;
  font-size: 22px;
}
.nuxt-content p {
  margin-bottom: 20px;
}
</style>
