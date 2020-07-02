<template>
  <v-row>
    <v-col class="pa-0">
      <!-- Hero Section -->
      <TheSplash
        headerText="Blog"
        imageSource="/images/vbanner.jpg"
        subText="Thoughts on Nuxt Content"
      />

      <v-container :class="[$breakpoint.mdAndUp ? 'px-12' : 'px-6']" fluid>
        <v-row>
          <v-col
            v-for="(blogPost, index) in blogPosts"
            :key="index"
            :class="$breakpoint.mdAndUp ? '' : 'mb-12'"
            cols="12"
            sm="6"
          >
            <v-card
              class="d-flex flex-column"
              height="100%"
              :flat="$breakpoint.smAndDown"
              :tile="$breakpoint.smAndDown"
            >
              <v-img
                src="/images/vbanner.jpg"
                lazy-src="https://lorempixel.com/400/200"
                max-height="200px"
              />
              <v-card-title
                :class="$breakpoint.mdAndUp ? 'display-1' : 'headline'"
                >{{ blogPost.title.substring(0, 70) }}</v-card-title
              >
              <v-card-subtitle
                :class="$breakpoint.mdAndUp ? 'subtitle-1' : 'body-2'"
                >{{ blogPost.description }}</v-card-subtitle
              >
              <v-btn
                class="mt-auto ml-3 mb-12 body-2"
                color="primary"
                :name="blogPost.title"
                nuxt
                max-width="200px"
                :to="`blog/${blogPost.slug}`"
                >Read more...</v-btn
              >
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-col>
  </v-row>
</template>
<script>
export default {
  head() {
    return {
      title: `Blog | Nuxt Netlify CMS Starter Kit`,
      meta: [
        {
          hid: `description`,
          name: "description",
          content: `A blog using Nuxt and Netlify CMS`
        }
      ]
    };
  },
  async asyncData({ $content }) {
    const blogPosts = await $content().fetch();
    return {
      blogPosts
    };
  }
};
</script>
<style lang="scss"></style>
