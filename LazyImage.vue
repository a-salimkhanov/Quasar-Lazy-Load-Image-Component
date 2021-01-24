<template>
  <span class=“relative-position” :class="spanClass" :style="spanStyle" v-intersection.once="onIntersection">
    <transition name="q-transition--scale">
      <img
        v-if="show"
        v-show="loaded"
        @load="loaded=true"
        :src="src"
        :title="title"
        :alt="title"
        :class="imgClass"
        :style="imgStyle" />
    </transition>
  </span>
</template>

<script>
export default {
  name: 'LazyImg',
  props: ['title', 'src', 'imgStyle', 'imgClass', 'spanClass', 'spanStyle'],
  data () {
    return {
      show: false,
      loaded: false
    }
  },
  methods: {
    onIntersection (entry) {
      if (entry.isIntersecting) {
        this.show = true
      }
    }
  }
}
</script>

<style lang=“scss” scoped>
</style>
