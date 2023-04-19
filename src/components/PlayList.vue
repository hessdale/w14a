<template>
  <div>
    <h1>PLAYLIST</h1>
    <section v-for="song in songs" :key="song.id">
      <button>PLAY {{ song.title }} by {{ song.artist }}</button>
    </section>
  </div>
</template>

<script>
export default {
  props: {
    songs: {
      type: Array,
    },
  },
};
</script>

<style scoped>
</style>