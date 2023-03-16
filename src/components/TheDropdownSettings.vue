<template>
  <div
    class="hidden group-hover:block flex flex-col absolute top-8 -right-full sm:right-0 bg-white w-72 border border-t-0"
  >
    <section class="py-2 border-b border-gray-200">
      <ul>
        <DropDownSettingsListItem
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
        <DropDownSettingsListItem label="Help" icon="help" with-sub-menu />
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
</template>

<script>
import BaseIcon from "./BaseIcon.vue";
import DropDownSettingsListItem from "./DropDownSettingsListItem.vue";

export default {
  components: {
    BaseIcon,
    DropDownSettingsListItem,
  },
};
</script>
