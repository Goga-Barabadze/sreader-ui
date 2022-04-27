<script setup lang="ts">
import {HomeIcon} from "@vue-icons/feather"
import {SettingsIcon} from "@vue-icons/feather"
import {HeartIcon} from "@vue-icons/feather"
import {BarChart2Icon} from "@vue-icons/feather"
</script>

<template>
  <div class="sidenav">
    <a href="#">
      <HomeIcon/>
    </a>
    <a href="#">
      <HeartIcon/>
    </a>
    <a href="#">
      <BarChart2Icon/>
    </a>
    <a href="#">
      <SettingsIcon/>
    </a>

    <!-- TODO: Add dynamic things like: show notes, export notes, export to anki -->
  </div>
</template>

<style lang="scss" scoped>

.sidenav {
  width: 70px;
  position: fixed;
  z-index: 1;
  top: 50%;
  transform: translateY(-50%);
  background-color: white;
  overflow: hidden;
  padding-top: 20px;
  box-shadow: 0 .3125rem .625rem 0 rgba(0, 0, 0, .08);

  display: flex;
  flex-direction: column;

  border-radius: 5px;
  align-items: center;
}

/* The navigation menu links */
.sidenav a {
  padding: 6px 8px 6px 16px;
  text-decoration: none;
  font-size: 25px;
  color: black;
}

.sidenav a:hover {
  fill: black;
}

.main {
  margin-left: 70px; /* Same as the width of the sidebar */
  padding: 0 10px;
}
</style>