<script setup>
import {ref} from "vue";
const showModal = ref(false);

</script>

<template>
  <button @click="showModal = !showModal"
          style="margin: 2px; padding: 8px; background-color: rgba(55,2,2,0.2) ; border-radius: 5px;">
    Show Modal
  </button>

  <div v-if="showModal" class="modal-wrapper modal-bg">
    <div class="modal">
      <p> Hello, I am modal</p>
    </div>
  </div>

</template>

<style scoped>
.modal-wrapper {
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  justify-content: center;
  align-items: center;
}
.modal-bg{
  background-color: rgba(0,0,0, 0.4);
}
.modal{
  background-color: white;
  position: relative;
  z-index: 2;
  padding: 5px;
  border-radius: 2px;
}
</style>
