<template>
  <v-container class="py-0" fluid>
    <v-row>
      <v-col class="pa-0">
        <!-- Hero Section -->
        <TheSplash
          :headerText="post.title"
          imageSource="/images/vbanner.jpg"
          :subText="post.description"
        />

        <article class="mb-12">
          <v-container class="py-6">
            <v-row>
              <v-col>
                <v-card
                  class="mx-auto"
                  flat
                  :width="$breakpoint.mdAndUp ? '75vw' : '90vw'"
                >
                  <template>
                    <h2 :class="$breakpoint.mdAndUp ? 'subtitle-1' : 'title'">
                      Table of Contents
                    </h2>
                    <ul>
                      <li
                        v-for="link of post.toc"
                        :key="link.id"
                        :class="{
                          toc2: link.depth === 2,
                          toc3: link.depth === 3
                        }"
                      >
                        <NuxtLink :to="`#${link.id}`">{{ link.text }}</NuxtLink>
                      </li>
                    </ul>
                  </template>
                  <nuxt-content :document="post" />
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </article>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  layout: "default",
  head() {
    let post = this.post;
    return {
      title: `${post.title} | Nuxt Netlify CMS Starter Kit`,
      meta: [
        {
          hid: `description`,
          name: "description",
          content: `${post.description}`
        }
      ]
    };
  },
  async asyncData({ $content, params }) {
    const post = await $content(params.blog).fetch();
    return {
      post
    };
  }
};
</script>
<style lang="scss" scoped></style>
