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
        "ml-auto",
        "-mt-1",
        "p-1",
        "opacity-0",
        "group-hover:opacity-100",
        "text-gray-500",
        "hover:text-gray-700",
        "focus:outline-none",
      ];
    },
    dropDownClasses() {
      return [
        "flex",
        "flex-col",
        "absolute",
        "-right-full",
        "sm:right-0",
        "bg-white",
        "w-48",
        "rounded",
        "shadow",
        "focus:outline-none",
        ...this.positionClasses,
      ];
    },
  },
  data() {
    return {
      isOpen: false,
      positionClasses: ["top-8"],
    };
  },
  watch: {
    isOpen() {
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
        return '-top-14';
      }

      if (window.innerHeight - coordY < dropdownHeight + btnHeight) {
        return 'top-0';
      }

      // тогда надо показать выпадайку НИЖЕ кнопки открытия
      return "top-9";
    },
    getRightClass() {

    },
    getLeftClass() {

    },
  },
};
</script>
