<script setup lang="ts">
import MediaContent from './components/MediaContent.vue'
import TextAnnotation from "./components/TextAnnotation.vue";
import Sidebar from './components/Sidebar.vue'
import {onMounted} from "vue";
import TorrentSearchApi from "torrent-search-api";

onMounted( () => {
  torrent()
})

async function torrent() {
  console.log(await TorrentSearchApi.search("Hello", "Books", 5))
}

</script>

<template>
  <!--
  <Sidebar />
  <MediaContent />
  <TextAnnotation/>
-->


</template>

<style lang="scss" scoped>
</style>
