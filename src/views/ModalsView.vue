<template>
  <div class="modals">
      <h1>Modals</h1>
      <button @click="showModal = true">Show Modal</button>
      <div
          class="modal"
          v-if="showModal"
      >
          <h1>This is a modal</h1>
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Assumenda autem ex laboriosam sequi voluptates. A
              ab inventore nobis. A alias aliquam dolor dolore ea eaque nihil omnis quis reiciendis tempore.</p>
          <button @click="showModal = false">Hide Modal</button>
      </div>
  </div>
</template>

<script setup>
/*
    imports
 */

    import {ref} from "vue";

/*
    modals
 */

    const showModal = ref(false)

</script>

<style scoped>
.modal{
    background: beige;
    padding: 10px;
    color: #282828;
}
</style>