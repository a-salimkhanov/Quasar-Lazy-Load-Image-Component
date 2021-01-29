<template>
  <span class=“relative-position” :class="spanClass" v-intersection.once="onIntersection">
    <transition name="q-transition--scale">
      <img
        v-show="loaded && intersect"
        @load="loaded=true"
        :src="intersect ? src : '/'"
        :title="title"
        :alt="title"
        :class="imgClass"
        :style="(loaded && intersect) ? imgStyle : ''" />
    </transition>
  </span>
</template>

<script>
export default {
  name: 'LazyImg',
  props: ['title', 'imgStyle', 'src', 'srclazy', 'imgClass', 'spanClass'],
  data () {
    return {
      loaded: false,
      intersect: false
    }
  },
  methods: {
    onIntersection (entry) {
      if (entry.isIntersecting) {
        this.loaded = false
        this.intersect = true
      }
    }
  }
}
</script>
<style lang=“sass” scoped></style>
