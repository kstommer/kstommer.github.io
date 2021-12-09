<template>
  <img class="album-cover" :src="cover">
</template>

<script>
export default {
  name: 'album-cover',
  props: {
    cover: {
      type: String,
			default: ''
		},
  }
}
</script>

<style scoped lang="scss">
.album-cover {
  width: 170px;
  height: 170px;
  background-color: gray;
  margin: auto;
  margin-right: 20px;
}
</style>
