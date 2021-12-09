<template>
  <article class="album-card">
    <album-cover :cover = "cover"/>
    <div class="album-card__info">
      <h1>{{title}}</h1>
      <album-info :release = "release" :price = "price"/>
    </div>
  </article>
</template>

<script>
import AlbumCover from '@/components/AlbumCover.vue'
import AlbumInfo from '@/components/AlbumInfo.vue'

export default {
  name: 'album-card',
  props: {
    album: {
      type: Object,
			required: true,
		},
  },
  components: {
    AlbumCover,
    AlbumInfo
  },
  data() {
    return {
      title: this.album.title.label,
      cover: this.album['im:image'][2].label,
      release: this.album['im:releaseDate'].attributes.label,
      price: this.album['im:price'].label
    }
  },
}
</script>

<style scoped lang="scss">
.album-card {
  width: 600px;
  height: 300px;
  margin: 0.75rem;
  padding: 20px;

  border-radius: 14px;
  background: #ffffff;

  display: flex;

  &__info {
    width: 100%;
    margin: auto;
    text-align: left;
  }

  &:hover {
    box-shadow: 5px 5px 5px 5px rgba(0, 0, 0, 0.07);
  }

  @media screen and (max-width: 600px) {
    display: block;
		height: initial;
    width: 100%;

    &__info {
      text-align: center;
    }
	}
}
</style>