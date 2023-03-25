<template>
  <aside
    class="hidden xl:block w-64 max-h-screen overflow-auto fixed top-0 pt-12 bg-white z-20"
  >
    <SideBarContent />
  </aside>
</template>

<script>
import SideBarContent from "./SideBarContent.vue";

export default {
  components: {
    SideBarContent,
  },
};
</script>
