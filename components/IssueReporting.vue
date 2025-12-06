<template>
  <button @click="toggle()" class="btn btn-neutral w-16 h-16 fixed bottom-3 right-20 rounded-full z-10">
    <font-awesome-icon :icon="['fab', 'github']" size="2x"/>
  </button>
</template>
<script setup lang="ts">
import {useLocalStorage} from "@vueuse/core";
import {FontAwesomeIcon} from "@fortawesome/vue-fontawesome";

const props = defineProps({
  host: {type:String, required:true},
  vendor: {type:String, required:true},
  name: {type:String, required:true},
});

const toggle = () => {
    window.open('https://'+props.host+'/'+props.vendor+'/'+props.name+'/issues/new', '_blank');
}
</script>