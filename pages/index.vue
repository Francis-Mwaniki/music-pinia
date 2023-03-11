<template>
  <div>
    <div class="flex justify-center items-center mx-auto flex-row">
      <h1 class="text-4xl text-pink-600">
        Your Favorite
        <span class="text-indigo-600 underline underline-offset-2 text-4xl">Music</span>
        In One Place
        <span class="text-7xl text-black underline">.</span>
      </h1>
    </div>
    <Music_api />
  </div>
</template>

<script>
import Music_api from "~~/components/Music_api.vue";

export default {
  name: "Index",
  data() {
    return {
      //
    };
  },
  methods: {
    //
  },
  mounted() {
    //
  },
  components: { Music_api },
};
</script>

<style scoped></style>
