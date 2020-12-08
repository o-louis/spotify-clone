<template>
  <section class="mt-16 text-white px-10 pt-3">
    <h1 class="font-bold text-2xl mb-6">Recently Played</h1>
    <div class="flex">
      <div
        v-for="song in songs"
        :key="song.title"
        class="bg-gray-darker p-4 rounded-md h-48 w-48 mr-6"
      >
        <img :src="song.image" :alt="song.title" class="rounded-sm" />
        <p class="font-bold mt-4 mb-2">{{ song.title }}</p>
        <p class="text-sm font-semibold opacity-70 leading-tight">
          {{ song.subtitle }}
        </p>
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from "vue";
export default {
  name: "Playlist",
  setup() {
    const songs = ref([
      {
        title: "Hip Hop Central",
        subtitle: "The names you know and the names you ne...",
        image: "image3.jpg",
      },
      {
        title: "Lo-Fi Beats",
        subtitle: "Beats to relax, study and focus.",
        image: "image2.jpg",
      },
      {
        title: "Christmas in Canada",
        subtitle: "The perfect soundtrack to the holiday season!",
        image: "image4.jpg",
      },
      {
        title: "Mood Booster",
        subtitle: "Get happy with today's dose of feel-good songs!",
        image: "image1.jpg",
      },
    ]);
    return {
      songs,
    };
  },
};
</script>
