<template>
  <div class="home p-0 m-0 position-relative">
    <HeaderVue />
    <HeroVue />
    <ExecutivesVue />
  </div>
</template>

<script>
import HeaderVue from "@/components/Header.vue";
import HeroVue from "@/components/Hero.vue";
import ExecutivesVue from "@/components/Executives.vue";
export default {
  name: "HomeView",
  components: {
    HeaderVue,
    HeroVue,
    ExecutivesVue,
  },
};
</script>
