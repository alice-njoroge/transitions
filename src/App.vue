<script setup>
import {ref} from "vue";

const showItems = ref(false)

const items = ref([
  {key: 1, value: 'one'},
  {key: 2, value: 'two'},
  {key: 3, value: 'three'},
]);

</script>

<template>
  <button @click="showItems = !showItems"
          style="margin: 2px; padding: 8px; background-color: rgba(200,0,89,0.2) ; border-radius: 5px;">
    {{ showItems ? 'Hide' : 'Show' }} Items
  </button>
  <transition>
    <ul v-if="showItems">
      <li v-for="item in items" :key="item.key"> {{ item.value }}</li>
    </ul>
  </transition>
</template>

<style scoped>

</style>
