<template>
  <section
    class="xl:pl-64 md:pl-24 pt-14 fixed bg-white bg-opacity-90 z-10 w-full"
  >
    <div class="border-t border-b px-4 max-w-screen-2xl m-auto">
      <div class="py-3 flex space-x-3 overflow-auto whitespace-nowrap">
        <a
          v-for="category in categories"
          :key="category"
          href=""
          class="text-sm px-3 py-1 inline-block rounded-full bg-gray-100 border border-gray-300 hover:bg-gray-200 transition"
        >
          {{ category }}
        </a>
      </div>
    </div>
  </section>
</template>
<script>
export default {
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
      ],
    };
  },
};
</script>
