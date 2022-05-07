<script setup lang="ts">
import MediaContent from './components/MediaContent.vue'
import TextAnnotation from "./components/TextAnnotation.vue";
import Sidebar from './components/Sidebar.vue'
import {computed, onMounted, ref} from "vue";
import TorrentSearchApi from "torrent-search-api";
import SearchField from "./components/SearchField.vue";
import JsonData from "./data.json";


const link = ref("");

async function search(searchText: string) {
  link.value = searchText

  // const WebTorrent = require('webtorrent')

  const client = new WebTorrent()

// Sintel, a free, Creative Commons movie
//   const torrentId = 'magnet:?xt=urn:btih:08ada5a7a6183aae1e09d831df6748d566095a10&dn=Sintel&tr=udp%3A%2F%2Fexplodie.org%3A6969&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969&tr=udp%3A%2F%2Ftracker.empire-js.us%3A1337&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337&tr=wss%3A%2F%2Ftracker.btorrent.xyz&tr=wss%3A%2F%2Ftracker.fastcast.nz&tr=wss%3A%2F%2Ftracker.openwebtorrent.com&ws=https%3A%2F%2Fwebtorrent.io%2Ftorrents%2F&xs=https%3A%2F%2Fwebtorrent.io%2Ftorrents%2Fsintel.torrent'
//   const torrentId = 'magnet:?xt=urn:sha1:YNCKHTQCWBTRNJIV4WNAE52SJUQCZO5C&dn=Great+Speeches+-+Martin+Luther+King+Jr.+-+I+Have+A+Dream.mp3'

  // client.add(torrentId, function (torrent: { infoHash: any; files: any[]; }) {
  //
  //   console.log('Client is downloading:', torrent.infoHash)
  //
  //   // Torrents can contain many files. Let's use the .mp4 file
  //   const file = torrent.files.find(function (file: { name: string; }) {
  //     console.log(file)
  //     return file.name.endsWith('.mp4')
  //   })
  //
  //   // Display the file by adding it to the DOM.
  //   // Supports video, audio, image files, and more!
  //   // file.appendTo('body')
  // })


}

const videoId = computed(() => {
  const regExp = /.*(?:youtu.be\/|v\/|u\/\w\/|embed\/|watch\?v=)([^#\&\?]*).*/;
  const match = link.value.match(regExp);
  return (match&&match[1].length==11)? match[1] : false;
})

onMounted(() => {
  // const word = 'erat pellentesque';
  // const page = document.body.innerHTML;
  // document.body.innerHTML = page.replace(new RegExp(word, "gi"), (match) => `<span class="highlighted">${match}</span>`);
  //
  // const elements = document.querySelectorAll('span')
  // elements.forEach(element => {
  //   element.className = 'highlighted'
  //   element.setAttribute("data-v-7ba5bd90", "")
  // })

  let externalScript = document.createElement('script')
  externalScript.setAttribute('src', 'https://cdn.jsdelivr.net/npm/webtorrent@latest/webtorrent.min.js')
  document.head.appendChild(externalScript)
})
</script>

<template>


<!--  <Sidebar />-->
<!--  <MediaContent />-->
<!--  <TextAnnotation/>-->

<SearchField
    class="search-field"
    @search="search"/>

<!--  <iframe v-if="link" width="720" height="405"-->
<!--          :src="`https://www.youtube.com/embed/${videoId}?enablejsapi=1&hl=en&modestbranding=1&playsinline=1`"-->
<!--          frameborder="0" allowfullscreen/>-->

<!--  <div class="highlightable">-->
<!--    Lorem ipsum <span class="highlighted">dolor</span> sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Sit amet commodo nulla facilisi nullam vehicula. A condimentum vitae sapien pellentesque habitant morbi. Nunc mi ipsum faucibus vitae aliquet nec ullamcorper sit amet. Massa tempor nec feugiat nisl. Enim ut tellus elementum sagittis vitae et leo. Sapien pellentesque habitant morbi tristique senectus et netus et malesuada. At erat pellentesque adipiscing commodo elit. Velit ut tortor pretium viverra suspendisse potenti nullam ac tortor. Tincidunt praesent semper feugiat nibh sed. Id aliquet risus feugiat in. Ac odio tempor orci dapibus. Auctor augue mauris augue neque gravida in. At tellus at urna condimentum mattis. Pulvinar neque laoreet suspendisse interdum consectetur libero. Risus pretium quam vulputate dignissim suspendisse in. Purus in mollis nunc sed id semper risus. Quisque sagittis purus sit amet volutpat consequat mauris nunc congue. Vitae sapien pellentesque habitant morbi tristique. Pharetra pharetra massa massa ultricies mi quis hendrerit. Donec ultrices tincidunt arcu non sodales neque sodales. Nec ullamcorper sit amet risus nullam eget felis eget nunc. Pellentesque habitant morbi tristique senectus et netus et malesuada. Vitae sapien pellentesque habitant morbi tristique senectus et netus. Etiam tempor orci eu lobortis elementum nibh tellus molestie. A iaculis at erat pellentesque adipiscing commodo. In mollis nunc sed id semper. Massa eget egestas purus viverra accumsan in nisl. Justo eget magna fermentum iaculis eu non diam phasellus vestibulum. Mattis molestie a iaculis at erat pellentesque adipiscing commodo. Lacus vestibulum sed arcu non odio euismod. Magna fermentum iaculis eu non diam phasellus vestibulum lorem sed. Convallis a cras semper auctor neque vitae tempus. Dui faucibus in ornare quam viverra orci sagittis. Dictumst vestibulum rhoncus est pellentesque elit ullamcorper dignissim. Vel facilisis volutpat est velit egestas dui id ornare arcu. Sit amet consectetur adipiscing elit ut aliquam purus sit amet. Imperdiet nulla malesuada pellentesque elit eget gravida. Turpis tincidunt id aliquet risus. Viverra ipsum nunc aliquet bibendum enim facilisis gravida. Sed viverra ipsum nunc aliquet bibendum enim facilisis. Eget mauris pharetra et ultrices. Cursus turpis massa tincidunt dui ut ornare lectus sit. Consectetur purus ut faucibus pulvinar elementum integer enim neque. Elementum pulvinar etiam non quam lacus suspendisse faucibus. Nibh cras pulvinar mattis nunc sed blandit. Auctor augue mauris augue neque gravida in fermentum et sollicitudin. Facilisis gravida neque convallis a cras semper auctor neque. Varius vel pharetra vel turpis nunc. Nunc eget lorem dolor sed viverra ipsum nunc aliquet.-->
<!--  </div>-->

</template>

<style lang="scss" scoped>
@import "styles/main";

.highlightable {
  margin: 6rem;
  line-height: 2.5rem;
  hyphens: auto;
  text-align: justify;
  font-size: 1.3rem;
}

.highlighted {
  cursor: pointer;
  color: $primary-green;
  background: $secondary-green;
  padding: 4px;
  border-radius: 5px;
}

.highlighted:hover {
  color: white;
  background: $primary-green;
}
</style>
