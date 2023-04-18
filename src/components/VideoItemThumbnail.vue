<template>
  <a href="">
    <div class="relative">
      <!-- <img : src="`https : // picsum . photos/seed/image$ { index } /720/404`" /> -->
      <img :src="`/22.jpg`" />
      <VideoItemThumbnailBtn icon="clock" label="Watch later" class="top-0" />
      <!-- <span
        class="bg-opacity-60 opacity-0 group-hover:opacity-100 absolute top-8 right-0 text-white bg-black rounded-sm m-1 p-1"
      >
        <BaseIcon name="menuAlt3" class="w-5 h-5" />
      </span> -->
      <VideoItemThumbnailBtn icon="menuAlt3" label="Add to queque" class="top-8" />
      <span
        class="duration-500 opacity-100 group-hover:opacity-0 absolute bottom-0 right-0 text-white bg-black text-xs rounded-sm m-1 p-1 font-semibold"
        >05:45</span
      >
    </div>
  </a>
</template>

<script>
import BaseIcon from "./BaseIcon.vue";
import VideoItemThumbnailBtn from "./VideoItemThumbnailBtn.vue";

export default {
  components: {
    BaseIcon,
    VideoItemThumbnailBtn,
  },

  props: ["index"],
};
</script>
