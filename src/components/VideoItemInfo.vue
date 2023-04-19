<template>
  <div class="flex items-start mr-3 mt-2 mb-7">
    <!-- <img
      :src="`https : // picsum . photos/seed/avatar $ { index } / 68`"
      class="rounded-full mr-3 w-9 h-9"
    /> -->
    <img :src="`/11.jpg`" class="rounded-full mr-3 w-9 h-9" />
    <div class="text-gray-800 text-sm">
      <span class="font-semibold">Video name</span>
      <div class="mt-1 flex items-center">
        <BaseTooltip :text="channelName" top>
          <span>{{ channelName }}</span>
        </BaseTooltip>
        <BaseTooltip text="Verified" top>
          <BaseIcon name="checkCircle" class="w-3.5 h-3.5 ml-1" />
        </BaseTooltip>
      </div>
      <div v-html="summary"></div>
    </div>

    <VideoItemDropdown />
  </div>
</template>

<script>
import BaseIcon from "./BaseIcon.vue";
import BaseTooltip from "./BaseTooltip.vue";
import VideoItemDropdown from "./VideoItemDropdown.vue";

export default {
  components: {
    BaseIcon,
    VideoItemDropdown,
    BaseTooltip,
  },

  props: ["index"],
  data() {
    return {
      channelName: `Chanel name ${this.index}`,
    };
  },

  computed: {
    summary() {
      const days = this.index === 1 ? "day" : "days";

      return ` ${this.index}K views&middot;${this.index} ${days} ago`;
    },
  },
};
</script>
