# Custom css
:::demo
```vue
<template>
   <div style='height: 100vh'>
      <vue-reader url='/vue-book-reader/files/啼笑因缘.epub' :getRendition="getRendition"/>
   </div>
</template>

<script setup>
//just need import { VueReader } from 'vue-book-reader'
import { defineClientComponent } from 'vitepress'
const VueReader = defineClientComponent(() => import('vue-book-reader'))
const getCSS = (style) => [
  `
    html {
      background: #000;
      color: #fff;
    }`,
]
const getRendition = async (rendition) => {
  const { book, renderer } = rendition
  renderer.setStyles(getCSS())
}
</script>
```
:::