<template>
  <div id="app">
    <!-- passing play to now playing  -->
    <now-playing :play="play"> </now-playing>
    <!-- passing songs added to playlist to playlist and app.vue listening for playsong from playlist -->
    <play-list :songs="songs" @play="playsong"> </play-list>
    <!-- app.vue listening for playlistadd -->
    <song-list @playlistAdd="addToPlaylist"> </song-list>
  </div>
</template>

<script>
//importing the seperate components
import NowPlaying from "@/components/NowPlaying.vue";
import PlayList from "@/components/PlayList.vue";
import SongList from "@/components/SongList.vue";

export default {
  //methods to hold functions
  methods: {
    //function for adding to play list by pushing onto an array of songs
    addToPlaylist: function (song) {
      this.songs.push(song);
    },
    //function for clearing and adding current playing song
    playsong: function (song) {
      this.play = undefined;
      this.play = song;
    },
  },
  //some empty variables for songs playlist(empty array) and playing song = undefined
  data() {
    return {
      songs: [],
      play: undefined,
    };
  },
  name: "App",
  components: {
    NowPlaying,
    PlayList,
    SongList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
