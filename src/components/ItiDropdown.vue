<template>
  <div class="dropdown">
    <slot></slot>
    <div v-if="!hidden" class="dropdown-menu">
      <slot name="menu"></slot>
    </div>

  </div>
</template>

<script setup lang="ts">

import { ref } from 'vue';



const hidden = ref(true);

const show = () => {
  hidden.value = false;
  window.addEventListener("click", onWindowClick);
};

const hide = () => {
  hidden.value = true;
  window.removeEventListener("click", onWindowClick);
};

const toggle = () => {
  hidden.value = !hidden.value;
  if(!hidden.value){
    setTimeout(() => {
	window.addEventListener("click", onWindowClick);
});
  }else {
    window.removeEventListener("click", onWindowClick);
  }
  
};

defineExpose({show,hide,toggle});
function onWindowClick(e: MouseEvent) {
  hide();
}
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
