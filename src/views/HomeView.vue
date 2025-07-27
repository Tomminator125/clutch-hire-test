<template>
  <nav>
    <img src="@/assets/GreenTechLogo.png" alt="GreenTech Logo" id="greentechlogo"/>
  </nav>
  <router-view />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ContactPage from "@/components/ContactPage.vue"; // @ is an alias to /src

export default defineComponent({
  name: "HomeView",
  components: {
    ContactPage,
  },
});
</script>
