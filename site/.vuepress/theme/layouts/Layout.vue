<template>
  <div>
    <Home v-if="$page.frontmatter.layout === 'home'"/>
  </div>  
</template>

<script>
import Home from '../components/Home.vue'

export default {
  components: { Home },

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
