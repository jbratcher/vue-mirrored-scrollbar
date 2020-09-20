<template>
  <v-container class="pa-0" fluid>
    <v-row>
      <v-col class="py-0 px-6">
        <!-- Hero Section -->
        <TheHero
          buttonOutline
          buttonText="Get Started"
          buttonTo="writing-content"
          dark
          headerText="Nuxt Content Static Starter"
          imageSource="/images/vbanner.jpg"
          subText="Quickly spin up a static site using Nuxt with Netlify CMS.
                  Push to deploy on Netlify."
        />
        <virtual-scroll
          height="20rem"
          width="0.5rem"
          target="content-1"
        ></virtual-scroll>
        <div class="content-container">
          <nuxt-content
            class="px-6"
            :class="$breakpoint.mdAndUp ? 'py-12' : 'py-6'"
            :document="hello"
            id="content-1"
          />
        </div>
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

<style lang="scss">
.content-container {
  min-height: 100vh;
}

.nuxt-content-container {
  max-height: 20rem;
  overflow-y: scroll;
}
</style>
