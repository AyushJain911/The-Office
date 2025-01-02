<template>
  <div v-if="data">
    <!-- <pre>{{ JSON.stringify(data, null, 2) }}</pre> -->
    <ul v-for="(item, index) in data">
      <li>{{ item.full_name }}</li>
      <img v-bind:src="item.image" alt="" />
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";
import axios from "axios";

const data = ref(null);

// const OfficeApi = "https://platform.buildwithhussain.dev/api/method/get-office";

const CORS_PROXY = "https://api.allorigins.win/raw?url="; //This is working fine
const OfficeApi = `${CORS_PROXY}https://platform.buildwithhussain.dev/api/method/get-office`;

axios
  .get(OfficeApi)
  .then((d) => (data.value = d.data.data))
  .catch((err) => console.error("Error Fetching data", err));

// fetch(OfficeApi)
//   .then((d) => d.json())
//   .then((msg) => console.log(msg));
</script>
