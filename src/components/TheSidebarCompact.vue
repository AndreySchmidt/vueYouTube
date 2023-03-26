<template>
  <aside :class="classes">
    <section>
      <ul>
        <SideBarCompactNavItem
          v-for="navItem in navList"
          :key="navItem.label"
          :label="navItem.label"
          :icon="navItem.icon"
          :is-active="navItem.isActive"
        />
      </ul>
    </section>
  </aside>
</template>

<script>
import SideBarCompactNavItem from "./SideBarCompactNavItem.vue";

export default {
  components: {
    SideBarCompactNavItem,
  },
  data() {
    return {
      navList: [
        {
          label: "Home",
          icon: "home",
          isActive: true,
        },
        {
          label: "Trending",
          icon: "trending",
          isActive: false,
        },
        {
          label: "Subscriptions",
          icon: "subscriptions",
          isActive: false,
        },
        {
          label: "Library",
          icon: "library",
          isActive: false,
        },
        {
          label: "History",
          icon: "history",
          isActive: false,
        },
      ],
    };
  },

  // props: {
  //   isOpen: Boolean,
  // },
  computed: {
    classes() {
      return [
        // this.isOpen ? "md:block" : "hidden",
        "min-h-screen",
        "overflow-auto",
        "fixed",
        "top-0",
        "pt-14",
        "bg-white",
        "z-20",
      ];
    },
  },
};
</script>
