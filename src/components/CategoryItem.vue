<template>
  <a href="" :class="classes">
    {{ category }}
  </a>
</template>

<script>
export default {
  props: ["category", "isActive"],

  computed: {
    classes() {
      const classes = [
        "text-sm",
        "px-3",
        "py-1",
        "inline-block",
        "rounded-full",
        "transition",
        "border",
      ];

      return this.isActive
        ? [
            ...classes,
            "border-gray-700",
            "hover:bg-gray-500",
            "bg-gray-600",
            "text-white",
          ]
        : [...classes, "border-gray-300", "hover:bg-gray-200", "bg-gray-100"];

      // border-gray-300 hover:bg-gray-200 bg-gray-100 text-white
      // const classes = [text-sm px-3 py-1 inline-block rounded-full bg-gray-100 border border-gray-300 hover:bg-gray-200 transition]
    },
  },
};
</script>
