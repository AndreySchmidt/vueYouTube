import TheDropdownApps from './TheDropdownApps.vue'; import TheDropdownApps from
'./TheDropdownApps.vue';

<template>
  <header class="flex fixed justify-between w-full z-30">
    <div class="flex lg:w-1/4">
      <div class="flex items-center xl:bg-white xl:w-64 pl-4">
        <button class="mr-3 sm:ml-2 sm:mr-6 focus:outline-none">
          <BaseIcon name="menu" />
        </button>
        <Logo />
      </div>
    </div>

    <TheSearch />

    <div
      class="flex items-center justify-end lg:w-1/4 sm:space-x-3 p-2 sm:px-4"
    >
      <button class="sm:hidden focus:outline-none p-2">
        <BaseIcon name="microphone" class="w-5 h-5" />
      </button>
      <button class="sm:hidden focus:outline-none">
        <BaseIcon name="search" class="w-5 h-5" />
      </button>
      <button class="relative group p-2 focus:outline-none">
        <svg
          enable-background="new 0 0 32 32"
          height="22px"
          id="Layer_1"
          version="1.1"
          viewBox="0 0 32 32"
          width="22px"
          xml:space="preserve"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
        >
          <g id="grid-2">
            <path
              d="M10.246,4.228c0-0.547-0.443-0.991-0.99-0.991H3.914c-0.548,0-0.991,0.443-0.991,0.991V9.57 c0,0.546,0.443,0.99,0.991,0.99h5.342c0.547,0,0.99-0.444,0.99-0.99V4.228z"
              fill="#515151"
            />
            <path
              d="M19.453,4.228c0-0.547-0.443-0.991-0.991-0.991h-5.343c-0.546,0-0.99,0.443-0.99,0.991V9.57 c0,0.546,0.444,0.99,0.99,0.99h5.343c0.548,0,0.991-0.444,0.991-0.99V4.228z"
              fill="#515151"
            />
            <path
              d="M28.868,4.228c0-0.547-0.443-0.991-0.99-0.991h-5.342c-0.548,0-0.991,0.443-0.991,0.991V9.57 c0,0.546,0.443,0.99,0.991,0.99h5.342c0.547,0,0.99-0.444,0.99-0.99V4.228z"
              fill="#515151"
            />
            <path
              d="M10.246,13.224c0-0.547-0.443-0.99-0.99-0.99H3.914c-0.548,0-0.991,0.443-0.991,0.99v5.342 c0,0.549,0.443,0.99,0.991,0.99h5.342c0.547,0,0.99-0.441,0.99-0.99V13.224z"
              fill="#515151"
            />
            <path
              d="M19.453,13.224c0-0.547-0.443-0.99-0.991-0.99h-5.343c-0.546,0-0.99,0.443-0.99,0.99v5.342 c0,0.549,0.444,0.99,0.99,0.99h5.343c0.548,0,0.991-0.441,0.991-0.99V13.224z"
              fill="#515151"
            />
            <path
              d="M28.868,13.224c0-0.547-0.443-0.99-0.99-0.99h-5.342c-0.548,0-0.991,0.443-0.991,0.99v5.342 c0,0.549,0.443,0.99,0.991,0.99h5.342c0.547,0,0.99-0.441,0.99-0.99V13.224z"
              fill="#515151"
            />
            <path
              d="M10.246,22.43c0-0.545-0.443-0.99-0.99-0.99H3.914c-0.548,0-0.991,0.445-0.991,0.99v5.344 c0,0.547,0.443,0.99,0.991,0.99h5.342c0.547,0,0.99-0.443,0.99-0.99V22.43z"
              fill="#515151"
            />
            <path
              d="M19.453,22.43c0-0.545-0.443-0.99-0.991-0.99h-5.343c-0.546,0-0.99,0.445-0.99,0.99v5.344 c0,0.547,0.444,0.99,0.99,0.99h5.343c0.548,0,0.991-0.443,0.991-0.99V22.43z"
              fill="#515151"
            />
            <path
              d="M28.868,22.43c0-0.545-0.443-0.99-0.99-0.99h-5.342c-0.548,0-0.991,0.445-0.991,0.99v5.344 c0,0.547,0.443,0.99,0.991,0.99h5.342c0.547,0,0.99-0.443,0.99-0.99V22.43z"
              fill="#515151"
            />
          </g>
        </svg>
        <TheDropdownApps />
      </button>
      <button class="relative group p-2 focus:outline-none">
        <BaseIcon name="dotsVertical" class="w-5 h-5" />
        <TheDropdownSettings />
      </button>
      <ButtonSignIn />
    </div>
  </header>
</template>

<script>
import TheDropdownApps from "./TheDropdownApps.vue";
import TheDropdownSettings from "./TheDropdownSettings.vue";
import TheSearch from "./TheSearch.vue";

import Logo from "./Logo.vue";
import ButtonSignIn from "./ButtonSignIn.vue";
import BaseIcon from "./BaseIcon.vue";

export default {
  components: {
    TheDropdownApps,
    TheDropdownSettings,
    TheSearch,
    Logo,
    ButtonSignIn,
    BaseIcon,
  },
};
</script>
