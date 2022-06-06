<script>
import Home from "./pages/Home.vue";
import { createRouter } from "vue-router";

const routes = [{ path: "/", component: Home }];
</script>

<template>
  <component :is="currentView" />
</template>

<style>
#app {
  font-family: "Poppins", sans-serif;
}
</style>
