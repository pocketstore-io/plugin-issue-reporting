<template>
  <button @click="toggle()" class="btn btn-neutral w-16 h-16 fixed bottom-3 right-20 rounded-full z-10">
    <font-awesome-icon :icon="['fab', 'github']" size="2x"/>
  </button>
</template>
<script setup lang="ts">
import {useLocalStorage} from "@vueuse/core";
import {FontAwesomeIcon} from "@fortawesome/vue-fontawesome";

const open = useLocalStorage('modal-bug-reporting', false);

const toggle = () => {
  if(!open.value)
    location.href = 'https://github.com/pocketstore-io/demo/issues/new';
  open.value = !open.value;
}

onMounted(() => {
  open.value = false;
});
</script>