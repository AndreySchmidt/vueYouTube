<template>
  <li>
    <a href="" :class="classesA">
      <BaseIcon :name="icon" :class="classesIcon" />
      <span> {{ label }} </span>
    </a>
  </li>
  <li>
    <a href="" class="flex items-center px-6 py-2 text-sm hover:bg-gray-100">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke-width="1.5"
        stroke="currentColor"
        class="w-6 h-6 mr-6"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M15.362 5.214A8.252 8.252 0 0112 21 8.25 8.25 0 016.038 7.048 8.287 8.287 0 009 9.6a8.983 8.983 0 013.361-6.867 8.21 8.21 0 003 2.48z"
        />
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M12 18a3.75 3.75 0 00.495-7.467 5.99 5.99 0 00-1.925 3.546 5.974 5.974 0 01-2.133-1A3.75 3.75 0 0012 18z"
        />
      </svg>
      <span> Trending </span>
    </a>
  </li>
  <li>
    <a href="" class="flex items-center px-6 py-2 text-sm hover:bg-gray-100">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke-width="1.5"
        stroke="currentColor"
        class="w-6 h-6 mr-6"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
        />
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M15.91 11.672a.375.375 0 010 .656l-5.603 3.113a.375.375 0 01-.557-.328V8.887c0-.286.307-.466.557-.327l5.603 3.112z"
        />
      </svg>
      <span> Subscriptions </span>
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
      const classes = ["w-6", "h-6", "mr-6"];

      return this.isActive ? [...classes, "text-red-600"] : [...classes];
    },
  },
};
</script>
