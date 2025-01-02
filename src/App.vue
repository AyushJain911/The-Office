<template>
  <header>
    <nav>
      <ul class="flex">
        <li class="m-2">Home</li>
        <li class="m-2">About</li>
      </ul>
    </nav>
  </header>

  <!-- By using props -->
  <!-- <Badge status="Paid" /> -->

  <!-- By using Slot -->
  <Badge> Active </Badge>

  <List />
</template>

<script setup>
import Badge from "./Badge.vue";
import List from "./List.vue";
</script>
