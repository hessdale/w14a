<template>
  <div>
    <h1>Songs</h1>
    <!-- using a loop to add the buttons in to add song to playlist -->
    <div v-for="song in songs" :key="song.id">
      <!-- event listener to each of the buttons -->
      <button @click="playlistAdd(song)">
        ADD {{ song.title }} - {{ song.artist }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    //using $emit to bubble up the info to the parent for adding a song to the playlist
    playlistAdd(song) {
      this.$emit(`playlistAdd`, song);
    },
  },
  //variables
  data() {
    return {
      //array of variables that have song info
      songs: [
        {
          title: `rare`,
          artist: `new spell`,
          id: 0,
          image_url: `https://images.pexels.com/photos/14844814/pexels-photo-14844814.jpeg?auto=compress&cs=tinysrgb&w=1600&lazy=load`,
        },
        {
          title: `expand`,
          artist: `energy patrol`,
          id: 1,
          image_url: `https://images.pexels.com/photos/10815995/pexels-photo-10815995.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1`,
        },
        {
          title: `break`,
          artist: `funeral`,
          id: 2,
          image_url: `https://images.pexels.com/photos/14691039/pexels-photo-14691039.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1`,
        },
        {
          title: `foster mayor`,
          artist: `cheap alchohol`,
          id: 3,
          image_url: `https://images.pexels.com/photos/15331169/pexels-photo-15331169.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1`,
        },
        {
          title: `tooth`,
          artist: `jet`,
          id: 4,
          image_url: `https://images.pexels.com/photos/14711412/pexels-photo-14711412.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1`,
        },
      ],
    };
  },
};
</script>

<style scoped>
</style>