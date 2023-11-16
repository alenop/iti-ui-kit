<template>
  <div class="dropdown">
    <div class="dropdown-menu"></div>
  </div>
</template>

<script setup lang="ts">
function onWindowClick(e: MouseEvent) {}
</script>
<style scoped>
.dropdown {
  position: relative;
}

.dropdown-menu {
  background: white;
  position: absolute;
  left: 0;
  border: 1px solid #ccc;
  border-radius: 5px;
}
</style>
