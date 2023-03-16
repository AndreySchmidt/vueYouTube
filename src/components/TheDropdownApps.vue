<template>
  <div
    class="hidden group-hover:block flex flex-col absolute top-8 right-0 sm:left-0 bg-white w-60 border border-t-0"
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
</template>

<script>
import DropDownListItem from "./DropDownListItem.vue";

export default {
  components: {
    DropDownListItem,
  },
};
</script>
