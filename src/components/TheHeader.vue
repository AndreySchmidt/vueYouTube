<template>
  <header class="flex fixed justify-between w-full z-30">
    <div class="flex lg:w-1/4">
      <div class="flex items-center xl:bg-white xl:w-64 pl-4">
        <button
          @click="$emit('toggleSidebar')"
          class="mr-3 sm:ml-2 sm:mr-6 focus:outline-none"
        >
          <BaseIcon name="menu" />
        </button>
        <Logo />
      </div>
    </div>
    <TheSearch />
    <div
      class="flex items-center justify-end lg:w-1/4 sm:space-x-3 p-2 sm:px-4"
    >
      <BaseTooltip text="Search with your vioce">
        <button class="sm:hidden focus:outline-none p-2">
          <BaseIcon name="microphone" class="w-5 h-5" />
        </button>
      </BaseTooltip>
      <BaseTooltip text="Search">
        <button class="sm:hidden focus:outline-none">
          <BaseIcon name="search" class="w-5 h-5" />
        </button>
      </BaseTooltip>
      <TheDropdownApps />

      <TheDropdownSettings />

      <ButtonSignIn />
    </div>
  </header>
</template>

<script>
import TheDropdownApps from "./TheDropdownApps.vue";
import TheDropdownSettings from "./TheDropdownSettings.vue";
import TheSearch from "./TheSearch.vue";

import Logo from "./Logo.vue";
import ButtonSignIn from "./ButtonSignIn.vue";
import BaseIcon from "./BaseIcon.vue";
import BaseTooltip from "./BaseTooltip.vue";

export default {
  components: {
    TheDropdownApps,
    TheDropdownSettings,
    TheSearch,
    Logo,
    ButtonSignIn,
    BaseIcon,
    BaseTooltip,
  },
  emits: {
    toggleSidebar: null,
  },
};
</script>
