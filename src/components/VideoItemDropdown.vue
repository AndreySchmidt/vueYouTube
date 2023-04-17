<template>
  <div class="relative ml-auto -mt-1">
    <button @click="toggle" :class="buttonClasses">
      <BaseIcon name="dotsVertical" />
    </button>
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
        @keydown.esc="isOpen = false"
        tabindex="-1"
        ref="dropdown"
        :class="dropDownClasses"
      >
        <section class="py-2">
          <ul>
            <VideoItemDropdownListItem label="Add to queue" icon="menuAlt3" />
          </ul>
        </section>
      </div>
    </transition>
  </div>
</template>

<script>
import { RESOLVE_FILTER } from "@vue/compiler-core";
import BaseIcon from "./BaseIcon.vue";
import VideoItemDropdownListItem from "./VideoItemDropdownListItem.vue";

export default {
  components: {
    BaseIcon,
    VideoItemDropdownListItem,
  },
  computed: {
    buttonClasses() {
      return [
        "p-1",
        "text-gray-500",
        "hover:text-gray-700",
        "focus:outline-none",
        this.isOpen? "opacity-100" : 'opacity-0',
        "group-hover:opacity-100",
      ];
    },
    dropDownClasses() {
      return [
        "flex",
        "flex-col",
        "absolute",
        // "top-8",
        // "-right-full",
        // "sm:right-0",
        "bg-white",
        "w-48",
        "rounded",
        "shadow",
        "focus:outline-none",
        "z-50",
        ...this.positionClasses,
      ];
    },
  },
  data() {
    return {
      isOpen: false,
      positionClasses: [],
    };
  },
  watch: {
    isOpen() {
      document.body.classList.toggle('overflow-hidden');
      this.$nextTick(() => this.isOpen && this.$refs.dropdown.focus());
    },
  },
  mounted() {
    window.addEventListener("click", (event) => {
      if (!this.$el.contains(event.target)) {
        this.isOpen = false;
      }
    });
  },
  methods: {
    toggle(event) {
      this.isOpen = !this.isOpen;

      if (this.isOpen) {
        this.$nextTick(
          () => (this.positionClasses = this.getPositionClasses(event))
        );
      }
    },
    getPositionClasses(event) {
      return [
        this.getTopClass(event),
        this.getRightClass(event),
        this.getBottomClass(event),
        this.getLeftClass(event),
      ];
    },
    getTopClass(event) {
      // вертикальная координата клика относительно всей страницы
      const coordY = event.clientY;
      // высота книпки открытия списка
      const btnHeight = event.currentTarget.offsetHeight;
      // высота выпадающего списка
      const dropdownHeight = this.$refs.dropdown.offsetHeight;

      // расстояние от клика до конца страницы
      if (window.innerHeight - coordY < dropdownHeight) {
        // тогда надо показать выпадайку выше кнопки открытия
        // return "-top-" + dropdownHeight;
        return '-top-auto';
        // return '-top-14';
      }

      if (window.innerHeight - coordY < dropdownHeight + btnHeight) {
        return 'top-0';
      }

      // тогда надо показать выпадайку НИЖЕ кнопки открытия
      return "top-9";
    },
    getBottomClass(event) {
      const coordY = event.clientY;
      const dropdownHeight = this.$refs.dropdown.offsetHeight;

      if (window.innerHeight - coordY < dropdownHeight) {
        return 'bottom-8';
      }
      return 'bottom-auto';
    },
    getRightClass(event) {
      const btnHeight = event.currentTarget.offsetHeight;

      const coordX = event.clientX;
      const coordY = event.clientY;

      const dropdownWidth = this.$refs.dropdown.offsetWidth;
      const dropdownHeight = this.$refs.dropdown.offsetHeight;
      
      if(window.innerWidth - coordX > dropdownWidth){
        return 'right-auto';
      }

      if(window.innerHeight - coordY > dropdownHeight + btnHeight){
        return 'right-0';
      }

      if(window.innerHeight - coordY > dropdownHeight){
        return 'right-8';
      }

      return 'right-0';
    },
    getLeftClass(event) {
      const btnHeight = event.currentTarget.offsetHeight;

      const coordX = event.clientX;
      const coordY = event.clientY;

      const dropdownHeight = this.$refs.dropdown.offsetHeight;
      const dropdownWidth = this.$refs.dropdown.offsetWidth;
      
      if(window.innerWidth - coordX < dropdownWidth){
        return 'left-auto';
      }

      if(window.innerHeight - coordY < dropdownHeight){
        return 'left-auto';
      }

      if(window.innerHeight - coordY > dropdownHeight + btnHeight){
        return 'left-auto';
      }

      return 'left-8';
    },
  },
};
</script>
