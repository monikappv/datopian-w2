<template>
  <div>
    <div class="banner image-section">
      <main class="banner relative">
        <header class="hero h-screen flex flex-row items-start pt-20 pr-40">
           <div class="container w-2/3">
          </div>
          <div class="container pb-16 w-1/3 pl-8 pt-8">
            <h1 class="text-4xl pb-2 font-medium" v-if="data.title !=='null'"> {{ data.title || 'Datopian' }}  </h1>
            <h2 class="text-2xl pb-8" v-if="data.heroText !=='null'"> {{ data.heroText || 'Datopian' }} </h2>
            <p class="description pb-6 text-lg">  
              {{ $page.frontmatter.tagline || $description || 'Welcome to Frictionless Data' }}
            </p>
            <div class="container inline">
              <button class="w-48 button-hero h-12 font-medium text-lg text-left pl-6 shadow-lg">Schedule a</button>
            </div>
          </div>
        </header>
      </main>
    </div>
    <div class="banner">
    <Content class="theme-default-content custom"/>
    </div>
  </div>  
</template>

<script>
export default {
  components: {  },

  computed: {
    data () {
      return this.$page.frontmatter
    },

    actionLink () {
      return {
        link: this.data.actionLink,
        text: this.data.actionText
      }
    }
  }
}
</script>

<style lang="stylus">

.button-hero {
  background-color: #505E5E;
  color: white;
  border-style: solid;
  cursor: pointer;
}

.image-section {
  background-image: url("/golden-gate-bridge.svg");
  background-size: cover;
  background-repeat: no-repeat;
}

</style>
