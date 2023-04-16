<template>
  <button
    @click="isOpen = !isOpen"
    class="relative group p-2 focus:outline-none"
  >
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
    <transition
      enter-active-class="transition ease-out duration-100"
      enter-from-class="transition opacity-0 scale-95"
      enter-to-class="transform opacity-100 scale-100"
      leave-active-class="transition ease-in duration-75"
      leave-from-class="transform opasity-100 scale-100"
      leave-to-class="transform opasity-0 scale-95"
    >
      <div
        v-show="isOpen"
        @keydown.esc="isOpen=false"
        tabindex="-1"
        ref="dropdown"
        class="flex flex-col absolute top-8 right-0 sm:left-0 bg-white w-60 border border-t-0 focus:outline-none"
      >
        <section class="py-2 border-b border-gray-200">
          <ul>
            <DropDownListItem label="YouTube TV" />
          </ul>
        </section>

        <section class="py-2 border-b border-gray-200">
          <ul>
            <DropDownListItem label="YouTube Music" />
            <DropDownListItem label="YouTube Kids" />
          </ul>
        </section>

        <section class="py-2">
          <ul>
            <DropDownListItem label="Creator Academy" />
            <DropDownListItem label="YouTube for Artists" />
          </ul>
        </section>
      </div>
    </transition>
  </button>
</template>

<script>
import DropDownListItem from "./DropDownListItem.vue";

export default {
  components: {
    DropDownListItem,
  },
  data() {
    return {
      isOpen: false,
    };
  },
  mounted() {
    window.addEventListener("click", (event) => {
      if (!this.$el.contains(event.target)) {
        this.isOpen = false;
      }
    });
  },
  watch: {
    isOpen() {
      this.$nextTick(() => this.isOpen && this.$refs.dropdown.focus());
    },
  },
};
</script>
