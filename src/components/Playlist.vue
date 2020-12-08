<template>
  <section :class="`text-white px-10 pt-3 ${subtitle ? 'mt-3' : 'mt-16'}`">
    <h1 class="font-bold text-2xl">{{ title }}</h1>
    <h2 v-if="subtitle" class="text-sm font-semibold opacity-70 mt-1">
      {{ subtitle }}
    </h2>
    <div :class="`grid grid-cols-6 gap-x-52 ${subtitle ? 'mt-4' : 'mt-5'}`">
      <div
        v-for="song in songs"
        :key="song.title"
        class="bg-gray-darker p-4 rounded-md w-48"
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
import { ref, computed } from "vue";
export default {
  name: "Playlist",
  props: {
    title: String,
    subtitle: String,
  },
  setup(props) {
    const playlist = ref([
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

    const customPlaylist = ref([
      {
        title: "Dork Diaries: Tales...",
        subtitle: "Rachel Renée Russell",
        image: "image5.jpg",
      },
      {
        title: "Scary Story Podcast",
        subtitle: "Scary Stories",
        image: "image6.jpg",
      },
      {
        title: "Something Scary",
        subtitle: "Studio71",
        image: "image7.jpg",
      },
      {
        title: "The Joe Rogan Ex...",
        subtitle: "Joe Rogan",
        image: "image8.jpg",
      },
      {
        title: "Sweet Boys",
        subtitle: "The Roots x Sweet Boys",
        image: "image9.jpg",
      },
    ]);

    const songs = computed(() => {
      return props.subtitle ? customPlaylist.value : playlist.value;
    });

    return {
      songs,
    };
  },
};
</script>
