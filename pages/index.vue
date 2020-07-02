<template>
  <v-container class="pa-0">
    <v-row>
      <v-col class="py-0">
        <!-- Hero Section -->
        <TheHero
          buttonOutline
          buttonText="Get Started"
          buttonTo="about"
          dark
          headerText="Nuxt Netlify CMS Starter Kit"
          imageSource="/images/vbanner.jpg"
          subText="Quickly spin up a static site using Nuxt with Netlify CMS.
                  Push to deploy on Netlify."
        />
        <nuxt-content class="py-6" :document="hello" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const hello = await $content("hello").fetch();
    return {
      hello
    };
  }
};
</script>

<style></style>
