<template>
  <ul class="flex-shrink-0 flex-col flex p-2">
    <img
      v-bind:src="props.image"
      alt="Character Name"
      style="display: block; height: 200px"
      class="aspect-auto"
    />
    <li class="mt-2 text-center font-mono text-xl font-bold">
      {{ props.name }}
    </li>
  </ul>
</template>

<script setup>
const props = defineProps({ name: String, image: String });
</script>
