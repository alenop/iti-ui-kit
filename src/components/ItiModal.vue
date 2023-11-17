<template>
    <div v-if="!hidden" class="iti-modal-wrapper" >
		<!-- En premier plan. Doit masquer la modal au click -->
<div @click="hide()" class="iti-modal-backdrop" ></div>
		
<div class="iti-modal">

<main class="iti-modal-body">
    <slot></slot>
				<!-- Injecter le slot par defaut -->
</main>

<footer class="iti-modal-footer" v-show="$slots.footer">
    <slot name="footer"></slot>
 <!-- Injecter le slot "footer" -->
</footer>

</div>

</div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
const hidden = ref(true);

const show = () => {
  hidden.value = false;
};

const hide = () => {
  hidden.value = true;
};

defineExpose({show,hide});
</script>

<style>
/**
 * Le wrapper prend tout l'écran
 */
.iti-modal-wrapper {
position: fixed;
top: 0;
left: 0;
width: 100%;
height: 100%;
display: flex;
justify-content: center;
align-items: center;
z-index: 100;
}

/**
 * La backdrop prend tout l'écran
 */
.iti-modal-backdrop {
position: fixed;
top: 0;
left: 0;
width: 100%;
height: 100%;
}

/**
 * La modal doit se trouver "au dessus" de la backdrop
 */
.iti-modal {
z-index: 101;
}

.iti-modal>.iti-modal-body {
}

.iti-modal>.iti-modal-footer {
}</style>
