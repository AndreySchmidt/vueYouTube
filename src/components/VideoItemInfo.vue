<template>
  <div class="flex items-start mr-3 mt-2 mb-7">
    <img
      :src="`https://picsum.photos/seed/avatar${index}/68`"
      class="rounded-full mr-3 w-9 h-9"
    />
    <div class="text-gray-800 text-sm">
      <span class="font-semibold">Video name</span>
      <div class="mt-1 flex items-center">
        <span>Chanel name {{ index }}</span>
        <BaseIcon name="checkCircle" class="w-3.5 h-3.5 ml-1" />
      </div>
      <div v-html="summary"></div>
    </div>

    <button
      class="ml-auto -mt-1 p-1 opacity-0 group-hover:opacity-100 text-gray-500 hover:text-gray-700 focus:outline-none"
    >
      <BaseIcon name="dotsVertical" />
    </button>
  </div>
</template>

<script>
import BaseIcon from "./BaseIcon.vue";

export default {
  components: {
    BaseIcon,
  },

  props: ["index"],

  computed: {
    summary() {
      const days = this.index === 1 ? "day" : "days";

      return ` ${this.index}K views&middot;${this.index} ${days} ago`;
    },
  },
};
</script>
