<template>
  <div
    class="hidden sm:flex flex-1 justify-end pl-8 md:pl-12 md:px-8 lg:px-0 items-center lg:w-1/2 max-w-md"
  >
    <div class="flex w-full h-full p-2.5">
      <TheSearchInput />
      <TheSearchButton />
    </div>
    <button class="ml-4 focus:outline-none">
      <BaseIcon name="microphone" class="w-5 h-5" />
    </button>
  </div>
</template>

<script>
import TheSearchButton from './TheSearchButton.vue';
import TheSearchInput from './TheSearchInput.vue';
import BaseIcon from './BaseIcon.vue';

export default {
    components: {
        TheSearchButton,
        TheSearchInput,
        BaseIcon
    }
};
</script>

