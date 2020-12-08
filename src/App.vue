<template>
  <div class="flex w-full bg-background h-screen overflow-hidden relative">
    <Navbar />
    <main class="w-full ml-56">
      <Header />
      <Playlist />
      <Playlist />
    </main>
    <Player />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar";
import Header from "@/components/Header";
import Player from "@/components/Player";
import Playlist from "@/components/Playlist";

export default {
  name: "App",
  components: {
    Navbar,
    Header,
    Player,
    Playlist,
  },
};
</script>

<style src="./assets/tailwind.css" />
