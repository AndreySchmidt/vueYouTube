<template>
  <TheSideBarMobileOverlay>
    <aside class="w-64 max-h-screen overflow-auto bg-white">
      <section class="flex items-center p-4 border-b sticky top-0 bg-white">
        <button class="mr-6 ml-2 focus:outline-none">
          <BaseIcon name="menu" />
        </button>
        <Logo />
      </section>
      <SideBarContent />
    </aside>
  </TheSideBarMobileOverlay>
</template>

<script>
import TheSideBarMobileOverlay from './TheSideBarMobileOverlay.vue';
import BaseIcon from './BaseIcon.vue';
import Logo from './Logo.vue';
import SideBarContent from "./SideBarContent.vue";

export default {
  components: {
    TheSideBarMobileOverlay,
    SideBarContent,
    Logo,
    BaseIcon,
  },
};
</script>