<template>
  <div id="app">
    <now-playing :current="current.song"> </now-playing>
    <play-list :songs="song"> </play-list>
    <song-list @playlist_add="add_to_playlist" @current="current"> </song-list>
  </div>
</template>

<script>
import NowPlaying from "@/components/NowPlaying.vue";
import PlayList from "@/components/PlayList.vue";
import SongList from "@/components/SongList.vue";

export default {
  methods: {
    current_song(song) {
      this.current = song;
    },
    add_to_playlist(song) {
      this.playlist = this.playlist + song;
    },
  },
  data() {
    return {
      current: {},
      songs: [],
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
