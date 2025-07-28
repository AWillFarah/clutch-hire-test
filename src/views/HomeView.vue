<template>
  <div class="home">
    <Form />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Form from "@/components/GTForm.vue"; // @ is an alias to /src

export default defineComponent({
  name: "HomeView",
  components: {
    Form,
  },
});
</script>
