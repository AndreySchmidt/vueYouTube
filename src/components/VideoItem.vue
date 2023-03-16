<template>
  <div class="group">
    <VideoItemThumbnail :index="index" />
    <VideoItemInfo :index="index" />
  </div>
</template>

<script>
import VideoItemThumbnail from "./VideoItemThumbnail.vue";
import VideoItemInfo from "./VideoItemInfo.vue";

export default {
  components: {
    VideoItemThumbnail,
    VideoItemInfo,
  },

  props: ["index"],
};
</script>
