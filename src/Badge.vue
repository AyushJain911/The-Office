<script setup>
import { computed, useSlots } from "vue";

const slot = useSlots();

const props = defineProps({
  status: String,
});

const statusToColor = {
  Active: "Green",
  Inactive: "Red",
  Pending: "Yellow",
  Unpaid: "Orange",
  Paid: "Pink",
};

const colorToClass = {
  Green: "bg-green-50 text-green-700",
  Red: "bg-red-50 text-red-700",
  Yellow: "bg-yellow-50 text-yellow-700",
  Orange: "bg-orange-50 text-orange-700",
  Pink: "bg-pink-50 text-pink-700",
};

// const statusColor = computed(() => {
//   const color = statusToColor[props.status];
//   return colorToClass[color] || "";
// });

const statusColor = computed(() => {
  const color = slot.default()[0].children.trim();
  return statusToColor[color];
});
</script>

<template>
  <!-- <span
    :class="[
      'inline-flex items-center rounded-md bg-green-50 px-2 py-1 text-xs font-medium text-green-700 ring-1 ring-inset ring-green-600/20',
      statusColor,
    ]"
    >{{ props.status }}</span
  > -->
  <span
    :class="[
      'inline-flex items-center rounded-md bg-green-50 px-2 py-1 text-xs font-medium text-green-700 ring-1 ring-inset ring-green-600/20',
      statusColor,
    ]"
    ><slot
  /></span>
</template>
