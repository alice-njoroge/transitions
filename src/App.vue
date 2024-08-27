<script setup>
import {ref} from "vue";

const showModal = ref(false);

</script>

<template>
  <button @click="showModal = !showModal"
          style="margin: 2px; padding: 8px; background-color: rgba(55,2,2,0.2) ; border-radius: 5px;">
    Show Modal
  </button>

 <Transition :duration="1400">
   <div v-if="showModal" class="modal-wrapper">
     <div class="modal-bg" @click="showModal = false"></div>
     <div class="modal">
       <p> Hello, I am modal</p>
     </div>
   </div>
 </Transition>

</template>

<style scoped>
.modal-wrapper .modal-bg {
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-bg {
  background-color: rgba(0, 0, 0, 0.4);
}

.modal {
  background-color: white;
  position: relative;
  z-index: 2;
  padding: 5px;
  border-radius: 2px;
}

.modal .modal-bg{
  transition: all 2s ease;
}
.v-enter-active .modal{
  transition-delay: 0.4s;
}
.v-leave-active .modal-bg{
  transition-delay: 0.4s;
}
.v-enter-from .modal-bg,
.v-leave-to .modal-bg{
  opacity: 0;
}
.v-enter-from .modal,
.v-leave-to .modal{
  opacity: 0;
  transform: translateX(-30px);
}
</style>
