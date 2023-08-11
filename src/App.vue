

<template>
  <div>{{ title }}</div>

  <input type="text" placeholder="MASUKKAN ALAMAT" v-model="alamat" />
  <button @click="test">PRESS ME PLEASE</button>
</template>

<style scoped>
</style>
<script setup>
import * as Vue from "vue"; // in Vue 3
import axios from "axios";
import VueAxios from "vue-axios";
import { ref } from "vue";
const title = ref("wkwk");

const base_url = ref("https://cek-ongkir.com/search?term=");
const result = ref([]);
const alamat = ref("");
const test = async () => {
  axios
    .get("https://cek-ongkir.com/search?term=manado", {
      headers: { "Access-Control-Allow-Origin": "*" },
    })
    .then((response) => {
      console.log(response.data);
      console.log("pepex");
    });
};
</script>