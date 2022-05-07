<script setup lang="ts">

</script>

<template>

  <div class="annotation">
    <div class="annotation-header">16:30, 10.12.2019</div>
    <div contentEditable="true" spellcheck="true">

    </div>
    <div class="annotation-footer"></div>
  </div>

</template>


<style lang="scss" scoped>
@import "src/styles/main";

.annotation {
  background-color: $secondary-blue;
  color: $primary-blue;

  padding: 1rem 1rem 1rem 1rem;
  margin: 3rem;

  position: absolute;
  right: 10px;

  width: fit-content;
  border-radius: 5px 0 0 5px;
  border-right-style: solid;
  border-right-width: 3px;

  max-width: 18rem;
  line-height: 1.5rem;
  overflow: hidden;

  box-shadow: 0 .3125rem .625rem 0 rgba(0, 0, 0, .08);
  transition: box-shadow 500ms;
}

.annotation:hover {
  box-shadow: 0 .3125rem .625rem 0 rgba(0, 0, 0, 0);
  transition: box-shadow 500ms;
}

.annotation-header {
  font-weight: 300;
  margin-bottom: 0.75rem;
}

.annotation-footer {
  margin-top: 0.75rem;
}

</style>
