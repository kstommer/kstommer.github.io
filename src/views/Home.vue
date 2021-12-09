<template>
  <div class="main">
    <h1>Top iTunes albums</h1>
    <album-gallery/>
  </div>
</template>

<script>
import AlbumGallery from '@/components/AlbumGallery.vue'

export default {
  name: 'Home',
  components: {
    AlbumGallery
  }
}
</script>

<style lang="scss">
.main {
  text-align: center;
  text-align: -webkit-center;
  min-height: 100vh;
}
</style>
