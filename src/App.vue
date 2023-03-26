<template>
  <!-- header start -->
  <TheHeader @toggle-sidebar="toggleSidebar" />
  <!-- header end -->
  <!-- sidebar md start -->
  <TheSidebarSmall :is-open="sidebarState === 'compact'" />
  <!-- sidebar md end -->
  <!-- sidebar main start -->
  <TheSidebar :is-open="sidebarState === 'normal'" />
  <!-- sidebar main end -->
  <!-- sidebar mobile start -->
  <TheSidebarMobile
    :is-open="isMobileSidebarOpen"
    @close="closeMobileSidebar"
  />
  <!-- sidebar mobile end -->
  <!-- category start -->
  <TheCategories :is-sidebar-open="sidebarState === 'normal'" />
  <!-- category end -->

  <!-- video start -->
  <TheVideoList :is-sidebar-open="sidebarState === 'normal'" />
  <!-- video end -->
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheSidebarSmall from "./components/TheSidebarSmall.vue";
import TheSidebar from "./components/TheSidebar.vue";
import TheSidebarMobile from "./components/TheSidebarMobile.vue";
import TheCategories from "./components/TheCategories.vue";
import TheVideoList from "./components/TheVideoList.vue";

export default {
  components: {
    TheHeader,
    TheSidebarSmall,
    TheSidebar,
    TheSidebarMobile,
    TheCategories,
    TheVideoList,
  },
  data() {
    return {
      isMobileSidebarOpen: false,
      sidebarState: null, // normal, compact
    };
  },
  methods: {
    toggleSidebar() {
      if (window.innerWidth > 1280) {
        this.sidebarState =
          this.sidebarState === "normal" ? "compact" : "normal";
      } else {
        this.openMobileSidebar();
      }
    },
    openMobileSidebar() {
      this.isMobileSidebarOpen = true;
    },
    closeMobileSidebar() {
      this.isMobileSidebarOpen = false;
    },
  },
  mounted() {
    if (window.innerWidth >= 768 && window.innerWidth < 1280) {
      this.sidebarState = "compact";
    }
    if (window.innerWidth > 1280) {
      this.sidebarState = "normal";
    }
  },
};
</script>
