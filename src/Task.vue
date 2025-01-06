<script setup>
import { ref } from "vue";
import About from "./About.vue";
import Team from "./Team.vue";

const currentTab = ref("about");
</script>

<template>
  <nav class="m-8">
    <ul class="flex">
      <li class="mr-8">
        <button
          :class="{
            active: currentTab === 'about',
          }"
          @click="currentTab = 'about'"
        >
          About
        </button>
      </li>
      <li class="mr-8">
        <button
          :class="{
            active: currentTab === 'team',
          }"
          @click="currentTab = 'team'"
        >
          Team
        </button>
      </li>
    </ul>
  </nav>

  <div class="section">
    <About v-if="currentTab === 'about'" />
    <Team v-if="currentTab === 'team'" />
  </div>
</template>
