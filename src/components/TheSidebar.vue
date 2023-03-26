<template>
  <aside :class="classes">
    <SideBarContent />
  </aside>
</template>

<script>
import SideBarContent from "./SideBarContent.vue";

export default {
  components: {
    SideBarContent,
  },
  props: {
    isOpen: Boolean,
  },
  computed: {
    classes() {
      return [
        this.isOpen ? "xl:block" : "hidden",
        "w-64",
        "min-h-screen",
        "overflow-auto",
        "fixed",
        "top-0",
        "pt-12",
        "bg-white",
        "z-20",
      ];
    },
  },
};
</script>
