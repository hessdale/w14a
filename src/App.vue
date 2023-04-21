<template>
  <div id="app">
    <now-playing :play="play"> </now-playing>
    <play-list :songs="songs" @play="playsong"> </play-list>
    <song-list @playlistAdd="addToPlaylist" @current="current"> </song-list>
  </div>
</template>

<script>
import NowPlaying from "@/components/NowPlaying.vue";
import PlayList from "@/components/PlayList.vue";
import SongList from "@/components/SongList.vue";

export default {
  methods: {
    addToPlaylist: function (song) {
      this.songs.push(song);
    },
    playsong: function (song) {
      this.play = undefined;
      this.play = song;
    },
  },
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
