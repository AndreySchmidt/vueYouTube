<template>
  <!-- header start -->
  <TheHeader @open-mobile-sidebar="openMobileSidebar" />
  <!-- header end -->
  <!-- sidebar md start -->
  <TheSidebarSmall />
  <!-- sidebar md end -->
  <!-- sidebar main start -->
  <TheSidebar />
  <!-- sidebar main end -->
  <!-- sidebar mobile start -->
  <TheSidebarMobile
    :is-open="isMobileSidebarOpen"
    @close="closeMobileSidebar"
  />
  <!-- sidebar mobile end -->
  <!-- category start -->
  <TheCategories />
  <!-- category end -->

  <main class="xl:ml-64 md:ml-24 pt-32 px-5 pb-5">
    <!-- video start -->
    <TheVideoList />
    <!-- video end -->
  </main>
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
    };
  },
  methods: {
    openMobileSidebar() {
      this.isMobileSidebarOpen = true;
    },
    closeMobileSidebar() {
      this.isMobileSidebarOpen = false;
    },
  },
};
</script>
