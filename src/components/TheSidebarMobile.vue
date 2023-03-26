<template>
  <transition
    enter-active-class="transition-opacity ease-linear duration-200"
    enter-from-class="opacity-0"
    enter-to-class="opacity-100"
    leave-active-class="transition-opacity ease-linear duration-200"
    leave-from-class="opacity-100"
    leave-to-class="opacity-0"
  >
    <TheSideBarMobileOverlay @click="$emit('close')" v-show="isOpen" />
  </transition>
  <transition
    enter-active-class="transition ease-in-out duration-200 transform"
    enter-from-class="-translate-x-full"
    enter-to-class="translate-x-0"
    leave-active-class="transition ease-in-out duration-200 transform"
    leave-from-class="translate-x-0"
    leave-to-class="-translate-x-full"
  >
    <aside
      v-show="isOpen"
      @keydown.esc="$emit('close')"
      tabindex="-1"
      ref="mobileSidebar"
      class="fixed w-64 max-h-screen overflow-auto bg-white outline-none z-50"
    >
      <section class="flex items-center p-4 border-b sticky top-0 bg-white">
        <button @click="$emit('close')" class="mr-6 ml-2 focus:outline-none">
          <BaseIcon name="menu" />
        </button>
        <Logo />
      </section>
      <SideBarContent />
    </aside>
  </transition>
</template>

<script>
import TheSideBarMobileOverlay from "./TheSideBarMobileOverlay.vue";
import BaseIcon from "./BaseIcon.vue";
import Logo from "./Logo.vue";
import SideBarContent from "./SideBarContent.vue";

export default {
  components: {
    TheSideBarMobileOverlay,
    SideBarContent,
    Logo,
    BaseIcon,
  },
  props: {
    isOpen: Boolean,
  },
  emits: {
    close: null,
  },
  watch: {
    isOpen() {
      this.$nextTick(() => this.isOpen && this.$refs.mobileSidebar.focus());

      // this.$nextTick(() => {
      //   if (this.isOpen) {
      //     this.$refs.mobileSidebar.focus();
      //   }
      // });
    },
  },
};
</script>
