<template>
  <li>
    <a href="" :class="classesA">
      <div class="mr-6 p-1 bg-gray-700 rounded-full">
        <BaseIcon :name="icon" :class="classesIcon" />
      </div>
      <span> {{ label }} </span>
    </a>
  </li>
</template>

<script>
import BaseIcon from "./BaseIcon.vue";

export default {
  components: {
    BaseIcon,
  },
  props: {
    isActive: Boolean,
    label: String,
    icon: String,
  },
  computed: {
    classesA() {
      const classes = ["flex", "items-center", "px-6", "py-2", "text-sm"];

      return this.isActive
        ? [
            ...classes,
            "text-red-600",
            "font-medium",
            "text-gray-800",
            "bg-gray-200",
            "hover:bg-gray-300",
          ]
        : [...classes, "hover:bg-gray-100"];
    },
    classesIcon() {
      const classes = ["w-4", "h-4"];

      return this.isActive ? [...classes, "text-red-600"] : [...classes, "text-white"];
    },
  },
};
</script>