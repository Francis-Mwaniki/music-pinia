<template>
  <div>
    <!-- Loop music on dezzers api -->
    <div v-for="item in music" :key="item.id">
      <div class="flex justify-center items-center mx-auto flex-row">
        <h1 class="text-4xl text-pink-600">
          {{ item.title }}
        </h1>
      </div>
      <!-- Audio -->
      <div class="flex justify-center items-center mx-auto flex-row bg-slate-600">
        <audio controls>
          <source src="https://www.deezer.com/playlist/45683464" type="audio/mpeg" />
        </audio>
      </div>
    </div>
    {{ music }}
  </div>
</template>

<script setup>
const music = ref([]);
const dezzer_url = "https://api.deezer.com/user/2529/playlists";
const fetchMusic = async () => {
  try {
    const res = await fetch(dezzer_url, {
      method: "GET",
      headers: {
        "Content-Type": "application/json",
      },
      Allow: "GET, POST, OPTIONS, PUT, PATCH, DELETE",
      "Allow-Headers": "X-Requested-With,content-type",
      "Allow-Methods": "GET, POST, OPTIONS, PUT, PATCH, DELETE",
      "Allow-control": "Access-Control-Allow-Origin",
      mode: "no-cors",
    });
    if (res.ok) {
      const data = await res.json();
      music.value = data;
      console.log(music.value);
    } else {
      const error = await res.json();
      console.log(error);
    }
  } catch (error) {
    console.log(error);
  }
};
fetchMusic();
</script>

<style scoped></style>
