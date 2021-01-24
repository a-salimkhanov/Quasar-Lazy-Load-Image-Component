# Quasar Lazy Load Image Component

Usage example:

```
<template>
  <lazyImg
    v-for="item in items"
    :key="item.id"
    :title="item.name"
    :spanClass="'q-mx-xs'"
    :imgStyle="'height: 40px; width: auto'"
    :src="item.image" />
</template>

<script>
export default {
  name: 'myItems',
  components: {
    lazyImg: () => import('components/LazyImage')
  },
  props: ['items']
}
</script>
  ```
  
