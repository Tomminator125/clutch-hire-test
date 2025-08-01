<template>
  <div class="home">
    <ContactPage v-if="!showThankYou" @submit="submissionHandler" />
    <ThankYou v-else/>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import ContactPage from "@/components/ContactPage.vue"; // @ is an alias to /src
import ThankYou from "@/components/ThankYou.vue";

export default defineComponent({
  name: "HomeView",
  components: {
    ContactPage,
    ThankYou,
  },
  setup() {
    const showThankYou = ref(false);

    const submissionHandler = () => {
      showThankYou.value = true;
      setTimeout(() => {
        showThankYou.value = false;
      }, 5000);
    };

    return {
      showThankYou,
      submissionHandler,
    };

  },
});
</script>
