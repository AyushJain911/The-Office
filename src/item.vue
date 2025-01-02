<template>
  <ul>
    <li>{{ props.name }}</li>
    <img
      v-bind:src="props.image"
      alt="Character Name"
      style="display: block; height: 200px"
      class="aspect-auto"
    />
  </ul>
</template>

<script setup>
const props = defineProps({ name: String, image: String });
</script>
