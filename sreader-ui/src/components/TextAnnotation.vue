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

.annotation {
  background-color: #CEE7FA;
  color: #217EB1;

  padding: 1rem 1rem 1rem 1rem;
  margin: 3rem;

  position: absolute;
  right: 10px;

  width: fit-content;
  border-radius: 5px 0 0 5px;
  border-right-style: solid;
  border-right-width: 0.1rem;

  max-width: 18rem;
  line-height: 1.5rem;
  overflow: hidden;

  box-shadow: 0 .3125rem .625rem 0 rgba(0, 0, 0, .08);
}

.annotation-header {
  font-weight: 300;
  margin-bottom: 0.75rem;
}

.annotation-footer {
  margin-top: 0.75rem;
}

</style>
