<template>
  <div>
    <div v-if="isPlaying != false">
      <h1>Now playing: {{ current.title }} by {{ current.artist }}</h1>
      <!-- using bind to get src from js current variable -->
      <img :src="current.image_url" alt="album art" height="250px" />
    </div>
    <!-- else it displays html -->
    <h1 v-else>Please play a song</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPlaying: false,
    };
  },
  props: {
    current: Object,
  },
};
</script>

<style scoped>
</style>