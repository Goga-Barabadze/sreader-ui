<script setup lang="ts">
  import {NavItem} from "epubjs";

  const props = withDefaults(
    defineProps<{
      items?: NavItem [];
      indentation?: number;
    }>(),{
      indentation: 0,
    }
  )

  const emits = defineEmits<{
    (e: "go-to-section", link: string): void;
  }>();

</script>

<template>

  <ul>
    <template v-for="item in items" :key="item.id">

      <li
          @click="emits('go-to-section', item.href)"
      >{{ item.label }}</li>

      <!-- TODO: Change me back to item.subitems -->
      <TableOfContents
          @GoToChapter="emits('go-to-section', item.href)"
          :items="item.subitems" />
    </template>
  </ul>

</template>


<style lang="scss" scoped>

@import "src/styles/main.scss";

</style>