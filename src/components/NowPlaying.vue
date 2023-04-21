<template>
  <div>
    <div v-if="play != undefined">
      <h1>Now playing: {{ play.title }} by {{ play.artist }}</h1>
      <!-- using bind to get src from props variable -->
      <img :src="play.image_url" alt="album art" height="250px" />
    </div>
    <!-- else it displays html -->
    <h1 v-else>Please play a song</h1>
  </div>
</template>

<script>
export default {
  //props imports playing song to display on html
  props: {
    play: {
      type: Object,
    },
  },
};
</script>

<style scoped>
</style>