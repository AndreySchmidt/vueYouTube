<template>
  <button
    class="flex items-center px-2 py-1 text-sm text-blue-700 uppercase border border-blue-700 rounded-sm whitespace-nowrap focus:outline-none"
  >
    <BaseIcon name="user" class="mr-2 w-7 h-7" />
    Sign In
  </button>
</template>

<script>
import BaseIcon from "./BaseIcon.vue";

export default {
  components: {
    BaseIcon,
  },
};
</script>
