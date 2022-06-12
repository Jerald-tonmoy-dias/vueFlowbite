<script>
import Home from "./pages/Home.vue";
import About from "./pages/About.vue";
import Service from "./pages/Service.vue";
import Contact from "./pages/Contact.vue";

const routes = {
  "/": Home,
  "/about": About,
  "/service": Service,
  "/contact": Contact,
};

export default {
  data() {
    return {
      currentPath: window.location.hash,
    };
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || "/"] || NotFound;
    },
  },
  mounted() {
    window.addEventListener("hashchange", () => {
      this.currentPath = window.location.hash;
    });
  },
};
</script>

<template>
  <!-- <Helloworld /> -->
  <!-- <Home /> -->
  <component :is="currentView" />
</template>

<style>
#app {
  font-family: "Poppins", sans-serif;
}
</style>
