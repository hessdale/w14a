<template>
  <div>
    <h1>PLAYLIST</h1>
    <!-- looping through the props variable songs to list the playlist -->
    <section v-for="song in songs" :key="song.id">
      <!-- adding event listener to each song to play from the playlist -->
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
      //variable currentsong undefined
      currentSong: undefined,
    };
  },

  methods: {
    //function to $emit the current song to the parent
    play(song) {
      this.currentSong = song;
      this.$emit(`play`, this.currentSong);
    },
  },
  //importing data for playist via props
  props: {
    songs: {
      type: Array,
    },
  },
};
</script>

<style scoped>
</style>