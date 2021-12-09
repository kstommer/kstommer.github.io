<template>
  <div class="album-gallery">
    <album-card v-for="(album, index) of albums" :key="index" :album="album"/>
  </div>
</template>

<script>
import AlbumCard from '@/components/AlbumCard.vue'

export default {
  name: 'album-gallery',
  props: {},
  components: {
    AlbumCard
  },
  data() {
    return {
      albums: []
    }
  },
  created(){
    fetch("https://itunes.apple.com/us/rss/topalbums/limit=100/json")
      .then(response => response.json())
      .then(data => {
        this.albums = data.feed.entry;
      })
      .catch(error => console.log(error));
  },
}
</script>

<style scoped lang="scss">
.album-gallery {
  display: flex;
  -webkit-box-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  align-items: center;
  flex-wrap: wrap;
  margin: 20px 0 100px;
  max-width: 1992px;

  @media screen and (max-width: 1024px) {
    padding: 0 10px;
	}
}
</style>