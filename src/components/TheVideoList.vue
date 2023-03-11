<template>
  <div
    class="grid gap-4 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 2xl:grid-cols-5 max-w-screen-2xl m-auto"
  >
    <!-- video item start -->
    <VideoItem v-for="i in 20" :key="i" :index="i" />
    <!-- video item end -->
  </div>
</template>

<script>
import VideoItem from "./VideoItem.vue";

export default {
  components: {
    VideoItem,
  },
};
</script>
