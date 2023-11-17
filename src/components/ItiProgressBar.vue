<script setup lang="ts">
import { computed } from 'vue';
const props = defineProps({
	progress: {
		type: Number,
		default: "Default"
  }
    ,color:{
        type:String,
        default:"Default"
    }
		//validator: (value: string)=> 
	})
  const colors:Map<String,String> = new Map();
  colors.set("Default","yellow");
  colors.set("primary","green");
  colors.set("secondary","red");
  const co = computed(() => [
    `${colors.get(props.color)}`,
]);
  const p = computed(() => [
    `${props.progress}`,
]);

  </script>

<template>
  <div :style="{width:'100%'}" class="progress-bar"><div :style="{width:p[0]+'%',height:15+'vh',backgroundColor:co[0]}" class="progress-bar-inner"><div  class = "progress-bar-inner-text">{{ p[0] }}%</div></div></div>

  
  </template>

<style scoped>
.progress-bar {
  background: var(--color-gray-light);
  border-radius: 50px;
  overflow: hidden;
}

.progress-bar > .progress-bar-inner {
  text-align: right;
  border-radius: 50px;
  /*width:100-v-bind(progress)+'%'*/
}

.progress-bar-inner-text {
  padding-top:35px;
  padding-right:25px;
}
</style>
