<template>
  <section :class="classes">
    <div class="border-t border-b px-4 max-w-screen-2xl m-auto">
      <div class="py-3 flex space-x-3 overflow-auto whitespace-nowrap">
        <CategoryItem
          v-for="category in categories"
          :key="category"
          :category="category"
          :is-active="category === 'All'"
        />
      </div>
    </div>
  </section>
</template>
<script>
import CategoryItem from "./CategoryItem.vue";

export default {
  components: {
    CategoryItem,
  },
  data() {
    return {
      categories: [
        "All",
        "Trucks",
        "Machines",
        "Engines",
        "Snow",
        "Ships",
        "Roads",
        "Tanks",
        "Buildings",
        "Tractors",
        "Football",
        "quam",
        "tempus",
        "consectetuer",
        "faucibus",
        "vulputate",
        "consequat",
        "massa",
        "elementum",
      ],
    };
  },
  props: {
    isSidebarOpen: Boolean,
  },
  computed: {
    classes() {
      return [
        this.isSidebarOpen ? "xl:pl-64" : "md:pl-24",
        "pt-14",
        "fixed",
        "bg-white",
        "bg-opacity-90",
        "z-10",
        "w-full",
      ];
    },
  },
};
</script>
