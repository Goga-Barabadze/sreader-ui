<script setup lang="ts">

import ePub from "epubjs";
import { onMounted, ref} from "vue";
import TableOfContents from "./TableOfContents.vue";
import type Navigation from "epubjs/types/navigation";

let pagesToRender = 2;

const book = ePub("https://s3.amazonaws.com/moby-dick/moby-dick.epub");
const rendition = book.renderTo("content", { allowScriptedContent: true, manager: "continuous", flow: "scrolled", width: "100%", height: "100%", snap: true });
rendition.display();



const navigation = ref({} as Navigation);

onMounted(() => {
  book.loaded.navigation.then((_navigation: Navigation) => {
    navigation.value = _navigation;
  });

  book.ready.then(() => {
    console.log("book ready");

  });

  rendition.on("rendered", (section: any) => {
    console.log("rendered");
  });

  rendition.on("relocated", (location: any) => {
    console.log("relocated");

  });

  rendition.on("layout", (layout: any) => {
    console.log("layout");
  });

  window.addEventListener("unload", () => {
    console.log("unloading");
  });

  window.onscroll = () => {
    let bottomOfWindow = Math.max(window.pageYOffset, document.documentElement.scrollTop, document.body.scrollTop) + window.innerHeight === document.documentElement.offsetHeight

    if (bottomOfWindow) {
      console.log('Next')
      rendition.next()
    }
  }
});

function goToSection(link: string) {
  console.log(link)
}

</script>

<template>

  <!--
  <TableOfContents
      @go-to-section="goToSection"
      :items="navigation.toc" />
      -->

  <div id="content" />

</template>

<style scoped lang="scss">
@import "src/styles/main.scss";

#content {
  background: $neutral-content-background-color;
  box-shadow: 0 .3125rem .625rem 0 rgba(0, 0, 0, .08);

  position: absolute;
  width: 50%;
  left: 50%;
  transform: translateX(-50%);
  padding-bottom: 500px;
  padding-top: 200px;

  z-index: -10;
}

</style>
