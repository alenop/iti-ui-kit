<template>
    <button :class="buttonClasses" class="iti-button">
        <slot></slot>
        
    </button>
</template>

<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps({
	color: {
		type: String,
		default: "Default"
		//validator: (value: string)=> 
	},shape:{
        type:String,
        default:"Default"
    }
});
const buttonShape = computed(() => [
    ,
]);
const buttonClasses = computed(() => [
    `button-color-${props.color}`,
    `button-shape-${props.shape}`
]);
</script>

<style scoped>
.button-shape-rounded {
    border-radius: 50px;
}
.button-shape-Default {
    border-radius: 0%;
}
.button-color-Default {
    background-color:azure
}
.button-color-primary {
    background-color:green
}
.button-color-secondary {
    background-color:red
}
.iti-button {
    
}

.iti-button:hover {
    background-color:blue;
}
</style>
