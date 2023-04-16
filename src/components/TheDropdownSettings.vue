<template>
  <button
    @click="isOpen = !isOpen"
    class="relative group p-2 focus:outline-none"
  >
    <BaseIcon name="dotsVertical" class="w-5 h-5" />
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
        class="flex flex-col absolute top-8 -right-full sm:right-0 bg-white w-72 border border-t-0"
      >
        <section class="py-2 border-b border-gray-200">
          <ul>
            <DropDownSettingsListItem
              v-for="item in list"
              :key="item.label"
              :label="item.label"
              :icon="item.icon"
              :with-sub-menu="item.withSubMenu"
            />

    <!-- <DropDownSettingsListItem
          label="Appearance: Light"
          icon="appearance"
          with-sub-menu
        />
        <DropDownSettingsListItem
          label="Language: English"
          icon="language"
          with-sub-menu
        />
        <DropDownSettingsListItem
          label="Location: Russia"
          icon="location"
          with-sub-menu
        />
        <DropDownSettingsListItem label="Help" icon="help" with-sub-menu /> -->
          </ul>
        </section>
        <section class="py-2">
          <ul>
            <DropDownSettingsListItem
              label="Restricted Mode: Off"
              with-sub-menu
            />
          </ul>
        </section>
      </div>
    </transition>
  </button>
</template>

<script>
import BaseIcon from "./BaseIcon.vue";
import DropDownSettingsListItem from "./DropDownSettingsListItem.vue";

export default {
  components: {
    BaseIcon,
    DropDownSettingsListItem,
  },
  data() {
    return {
      isOpen: false,
      list: [
        {
          label: "Appearance: Light",
          icon: "appearance",
          withSubMenu: true,
        },
        {
          label: "Language: English",
          icon: "language",
          withSubMenu: true,
        },
        {
          label: "Location: Russia",
          icon: "location",
          withSubMenu: true,
        },
        {
          label: "Help",
          icon: "help",
          withSubMenu: true,
        },
      ],
    };
  },
  mounted() {
    window.addEventListener("click", (event) => {
      if (!this.$el.contains(event.target)) {
        this.isOpen = false;
      }
    });
  },
};
</script>
