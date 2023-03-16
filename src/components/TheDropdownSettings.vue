<template>
  <div
    class="hidden group-hover:block flex flex-col absolute top-8 -right-full sm:right-0 bg-white w-72 border border-t-0"
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
        <DropDownSettingsListItem label="Restricted Mode: Off" with-sub-menu />
      </ul>
    </section>
  </div>
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
};
</script>
