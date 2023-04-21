<template>
  <TheSearch />
  <div class="flex items-center justify-end lg:w-1/4 sm:space-x-3 p-2 sm:px-4">
    <BaseTooltip text="Search with your vioce">
      <button class="sm:hidden focus:outline-none p-2">
        <BaseIcon name="microphone" class="w-5 h-5" />
      </button>
    </BaseTooltip>
  </div>
</template>

<script>
import TheSearch from "./TheSearch.vue";
import BaseTooltip from "./BaseTooltip.vue";
import BaseIcon from "./BaseIcon.vue";

export default {
  components: {
    BaseIcon,
    BaseTooltip,
    TheSearch,
  },
};
</script>
<!-- Vue JS Tailwind CSS YouTube клон #28 - Компонент для мобильного поиска -->