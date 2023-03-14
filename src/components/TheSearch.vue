<template>
  <div
    class="hidden sm:flex flex-1 justify-end pl-8 md:pl-12 md:px-8 lg:px-0 items-center lg:w-1/2 max-w-md"
  >
    <div class="flex w-full h-full p-2.5">
      <TheSearchInput />
      <TheSearchButton />
    </div>
    <button class="ml-4 focus:outline-none">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke-width="1.5"
        stroke="currentColor"
        class="w-5 h-5"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M12 18.75a6 6 0 006-6v-1.5m-6 7.5a6 6 0 01-6-6v-1.5m6 7.5v3.75m-3.75 0h7.5M12 15.75a3 3 0 01-3-3V4.5a3 3 0 116 0v8.25a3 3 0 01-3 3z"
        />
      </svg>
    </button>
  </div>
</template>

<script>
import TheSearchButton from './TheSearchButton.vue';
import TheSearchInput from './TheSearchInput.vue';

export default {
    components: {
        TheSearchButton,
        TheSearchInput
    }
};
</script>

