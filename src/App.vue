<template>
  <!-- header start -->
  <TheHeader @toggle-sidebar="toggleSidebar" />
  <!-- header end -->
  <!-- sidebar md start -->
  <TheSidebarCompact v-if="isCompactSidebarOpen" />
  <!-- sidebar md end -->
  <!-- sidebar main start -->
  <TheSidebar v-if="isSidebarOpen" />
  <!-- sidebar main end -->
  <!-- sidebar mobile start -->
  <TheSidebarMobile
    :is-open="isMobileSidebarOpen"
    @close="closeMobileSidebar"
  />
  <!-- sidebar mobile end -->
  <!-- category start -->
  <TheCategories :is-sidebar-open="isSidebarOpen" />
  <!-- category end -->

  <!-- video start -->
  <TheVideoList :is-sidebar-open="isSidebarOpen" />
  <!-- video end -->
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheSidebarCompact from "./components/TheSidebarCompact.vue";
import TheSidebar from "./components/TheSidebar.vue";
import TheSidebarMobile from "./components/TheSidebarMobile.vue";
import TheCategories from "./components/TheCategories.vue";
import TheVideoList from "./components/TheVideoList.vue";

export default {
  components: {
    TheHeader,
    TheSidebarCompact,
    TheSidebar,
    TheSidebarMobile,
    TheCategories,
    TheVideoList,
  },
  data() {
    return {
      isCompactSidebarAtcive: false, // normal, compact
      isMobileSidebarOpen: false,
      isCompactSidebarOpen: false,
      isSidebarOpen: false,
    };
  },
  methods: {
    onResize() {
      if (window.innerWidth < 768) {
        this.isCompactSidebarOpen = false;
        this.isSidebarOpen = false;
      } else if (window.innerWidth < 1280) {
        this.isCompactSidebarOpen = true;
        this.isSidebarOpen = false;
      } else {
        this.isCompactSidebarOpen = this.isCompactSidebarAtcive;
        this.isSidebarOpen = !this.isCompactSidebarAtcive;
        this.isMobileSidebarOpen = false;
      }
    },
    toggleSidebar() {
      if (window.innerWidth > 1280) {
        this.isCompactSidebarAtcive = !this.isCompactSidebarAtcive;
        this.onResize();
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
    this.onResize();
    window.addEventListener("resize", this.onResize);
  },
};
</script>
