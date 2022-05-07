<script setup lang="ts">
import {SearchIcon} from "@vue-icons/feather"
import {ref} from "vue";

const emit = defineEmits<{
  (e: 'search', search: string): void
}>()

const searchText = ref("")

</script>

<template>
  <div class="search-box" @keydown.enter="emit('search', searchText)">
    <input class="search-input" aria-label="Search" autocomplete="off" spellcheck="false" placeholder="Search..." v-model="searchText"/>
    <div class="search-button" @click="emit('search', searchText)">
      <SearchIcon class="search-icon"/>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "src/styles/main.scss";

.search-box {
  display: flex;
  margin-left: 20%;
  margin-right: 20%;
}

.search-button {
  color: darkgray;
  flex-grow: 0.5;
  background: rgba(0,0,0,.05);
  line-height: 1.8rem;
  padding: 4px 4px 4px 20px;
  border-radius: 0 14px 14px 0;
}

.search-button:hover{
  background: $primary-color;
  color: white;
}

.search-icon {
  position: relative;
  left: 40%;
  top: 10%;
  transform: translateX(-60%);
}

.search-input {
  margin: 0;
  flex-grow: 15;
  cursor: text;
  font-size: .85rem;
  line-height: 1.8rem;
  outline: none;
  background: rgba(0,0,0,.05);
  background-size: 1rem;
  border: 0;
  padding: 4px 4px 4px 20px;
  border-radius: 14px 0 0 14px;
}
</style>