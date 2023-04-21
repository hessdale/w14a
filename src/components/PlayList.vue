<template>
  <div>
    <h1>PLAYLIST</h1>
    <section v-for="song in songs" :key="song.id">
      <button @click="play(song)">
        PLAY {{ song.title }} by {{ song.artist }}
      </button>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentSong: undefined,
    };
  },

  methods: {
    play(song) {
      this.currentSong = song;
      this.$emit(`play`, this.currentSong);
    },
  },
  props: {
    songs: {
      type: Array,
    },
  },
};
</script>

<style scoped>
</style>